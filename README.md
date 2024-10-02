# OpenSC documentation

Manual pages for the
[OpenSC command line tools](https://htmlpreview.github.io/?https://github.com/OpenSC/OpenSC/blob/master/doc/tools/tools.html)
as well as for the
[OpenSC configuration files](https://htmlpreview.github.io/?https://github.com/OpenSC/OpenSC/blob/master/doc/files/files.html)
are available online and typically distributed along with your installation.

The [OpenSC Wiki](https://github.com/OpenSC/OpenSC/wiki) includes, among others, information for:
 * [Windows Quick Start](https://github.com/OpenSC/OpenSC/wiki/Windows-Quick-Start)
 * [macOS Quick Start](https://github.com/OpenSC/OpenSC/wiki/macOS-Quick-Start)
 * [Compiling and Installing on Unix flavors](https://github.com/OpenSC/OpenSC/wiki/Compiling-and-Installing-on-Unix-flavors)
 * [Frequently Asked Questions](https://github.com/OpenSC/OpenSC/wiki/Frequently-Asked-Questions)
 * More user and developer provided documentation

# Downloads

## Latest release

The [latest stable version of OpenSC](https://github.com/OpenSC/OpenSC/releases/latest) is available on Github.  It is available as

 * Windows installer for 64 bit and 32 bit programs (`OpenSC*_win64.msi` and `OpenSC*_win32.msi`)
 * macOS installer (`OpenSC*.dmg`)
 * Source code distribution (`opensc*.tar.gz`)

## Nightly build

The latest source code is available through [GitHub](https://github.com/OpenSC/OpenSC/archive/master.zip).
Nightly builds are available by their git hash in branches of [OpenSC/Nightly](https://github.com/OpenSC/Nightly).


# Build and testing status

[![Linux build](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml/badge.svg)](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml)
[![OSX build](https://github.com/OpenSC/OpenSC/actions/workflows/macos.yml/badge.svg)](https://github.com/OpenSC/OpenSC/actions/workflows/macos.yml)
[![AppVeyor CI Build Status](https://ci.appveyor.com/api/projects/status/github/OpenSC/OpenSC?branch=master&svg=true)](https://ci.appveyor.com/project/frankmorgner/opensc/branch/master)
[![Coverity Scan Status](https://scan.coverity.com/projects/4026/badge.svg)](https://scan.coverity.com/projects/4026)
[![CodeQL](https://github.com/OpenSC/OpenSC/actions/workflows/codeql.yml/badge.svg?event=push)](https://github.com/OpenSC/OpenSC/actions/workflows/codeql.yml)
[![Fuzzing Status](https://oss-fuzz-build-logs.storage.googleapis.com/badges/opensc.svg)](https://bugs.chromium.org/p/oss-fuzz/issues/list?sort=-opened&can=1&q=proj:opensc)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/3908/badge)](https://bestpractices.coreinfrastructure.org/projects/3908)

Build and test status of specific cards:

| Cards                                                               | Status                                                                                                                            |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| CAC                                                                 | [![CAC](https://gitlab.com/redhat-crypto/OpenSC/badges/cac/pipeline.svg)](https://gitlab.com/redhat-crypto/OpenSC/pipelines)      |
| [virt_CACard](https://github.com/Jakuje/virt_cacard)                | [![virt_CACard](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml/badge.svg)](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml) |
| [Coolkey](https://github.com/dogtagpki/coolkey/tree/master/applet)  | [![Coolkey](https://gitlab.com/redhat-crypto/OpenSC/badges/coolkey/pipeline.svg)](https://gitlab.com/redhat-crypto/OpenSC/pipelines) |
| [PivApplet](https://github.com/arekinath/PivApplet)                 | [![PIV](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml/badge.svg)](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml) |
| [OpenPGP Applet](https://github.com/Yubico/ykneo-openpgp/)          | [![OpenPGP](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml/badge.svg)](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml) |
| [GidsApplet](https://github.com/vletoux/GidsApplet/)                | [![GIDS](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml/badge.svg)](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml) |
| [IsoApplet](https://github.com/philipWendland/IsoApplet/)           | [![IsoApplet](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml/badge.svg)](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml) |
| [OsEID (MyEID)](https://sourceforge.net/projects/oseid/)            | [![OsEID (MyEID)](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml/badge.svg)](https://github.com/OpenSC/OpenSC/actions/workflows/linux.yml) |
| SmartCardHSM                                                        | [![SmartCardHSM](https://gitlab.com/redhat-crypto/OpenSC/badges/sc-hsm/pipeline.svg)](https://gitlab.com/redhat-crypto/OpenSC/pipelines) |
| ePass2003                                                           | [![ePass2003](https://gitlab.com/redhat-crypto/OpenSC/badges/epass2003/pipeline.svg)](https://gitlab.com/redhat-crypto/OpenSC/pipelines) |

# Windows x64 Build Guide

This guide provides instructions on how to build `OpenSC.msi` from the OpenSC-0.26.1-rc1 source code.

## Software Requirements:

- **Visual Studio 2017**
- **MSYS2**
- **Windows Kits 10**

---

## Step 1: Setup

1. **Download, extract, and rename the following libraries exactly as specified:**
   - [Zlib v1.2.12](https://github.com/madler/zlib/archive/v1.2.12.zip) → `C:\zlib`
   - [OpenPACE v1.1.3](https://github.com/frankmorgner/openpace/archive/1.1.3.zip) → `C:\openpace`
   - [OpenSSL v1.1.1](https://github.com/greenpau/openssl-binaries/blob/master/Win64OpenSSL-1_1_1a.msi) → `C:\OpenSSL-Win64`

2. **Create a new folder**: `C:\projects`

3. **Download and extract OpenSC v0.26.1**:
   - [OpenSC v0.26.1-rc1](https://github.com/OpenSC/OpenSC/releases) → `C:\projects`

4. **Install Winx:**
   - Download and install from [WiX Toolset](https://github.com/wixtoolset/wix3/releases)

5. **Install CPDK:**
   - Download and install [CPDK](https://download.microsoft.com/download/1/7/6/176909B0-50F2-4DF3-B29B-830A17EA7E38/CPDK_RELEASE_UPDATE/cpdksetup.exe)

---

## Step 2: Setup Environment Variables

1. **Open** "Edit the system environment variables" on your system.

2. **Create new system variables:**

   | Variable Name     | Value                       |
   |-------------------|-----------------------------|
   | ZLIB_INCL_DIR     | `C:\zlib`                   |
   | ZLIB_VER_DOT      | `1.2.12`                    |
   | OPENPACE_DIR      | `C:\openpace`               |
   | OPENSSL           | `C:\OpenSSL-Win64`          |
   | OPENSSL_DIR       | `C:\OpenSSL-Win64`          |
   | WIX               | `C:\Program Files (x86)\WiX Toolset v3.14` (Check your path) |

3. **Update the `Path` system variable** to include the following paths:

   - `C:\OpenSSL-Win64\bin`
   - `C:\openpace\`
   - `C:\zlib\`
   - `C:\Program Files (x86)\Windows Kits\10\bin\10.0.17763.0\x64` (Check your path)

---

## Step 3: Build Process

1. **Modify `Makefile.msc` in the zlib directory:**

   - Open the file `C:\zlib\win32\Makefile.msc` in a text editor.
   - Find the following line:
     ```bash
     CFLAGS = -nologo -MD -W3 -O2 -Oy- -Zi -Fd"zlib" $(LOC)
     ```
   - Replace it with:
     ```bash
     CFLAGS = -nologo -MT -W3 -O2 -Oy- -Zi -Fd"zlib" $(LOC)
     ```
2. **Open** "Developer Command Prompt for Visual Studio 2017" **as Administrator**.

   - Find the path to `vcvarsall.bat` in your installed Visual Studio 2017 folder.
   - Run the following command:  
     `call "path_to_your_file\vcvarsall.bat" x64`

3. **Build Zlib:**

   - In the Developer Command Prompt, run the following commands:
     ```bash
     cd C:\zlib
     nmake /nologo -f win32/Makefile.msc zlib.lib
     ```

4. **Build OpenPACE:**

   - Navigate to `C:\openpace\src` and run:
     ```bash
     cl /nologo /IC:\OpenSSL-Win64\include /I. /DX509DIR=\"/\" /DCVCDIR=\"/\" /W3 /D_CRT_SECURE_NO_DEPRECATE /DWIN32_LEAN_AND_MEAN /GS /MT /DHAVE_ASN1_STRING_GET0_DATA=1 /DHAVE_DECL_OPENSSL_ZALLOC=1 /DHAVE_DH_GET0_KEY=1 /DHAVE_DH_GET0_PQG=1 /DHAVE_DH_SET0_KEY=1 /DHAVE_DH_SET0_PQG=1 /DHAVE_ECDSA_SIG_GET0=1 /DHAVE_ECDSA_SIG_SET0=1 /DHAVE_EC_KEY_METHOD=1 /DHAVE_RSA_GET0_KEY=1 /DHAVE_RSA_SET0_KEY=1 /DHAVE_EC_POINT_GET_AFFINE_COORDINATES=1 /DHAVE_EC_POINT_SET_AFFINE_COORDINATES=1 /c ca_lib.c cv_cert.c cvc_lookup.c x509_lookup.c eac_asn1.c eac.c eac_ca.c eac_dh.c eac_ecdh.c eac_kdf.c eac_lib.c eac_print.c eac_util.c misc.c pace.c pace_lib.c pace_mappings.c ri.c ri_lib.c ta.c ta_lib.c objects.c ssl_compat.c
     lib /nologo /out:libeac.lib ca_lib.obj cv_cert.obj cvc_lookup.obj x509_lookup.obj eac_asn1.obj eac.obj eac_ca.obj eac_dh.obj eac_ecdh.obj eac_kdf.obj eac_lib.obj eac_print.obj eac_util.obj misc.obj pace.obj pace_lib.obj pace_mappings.obj ri.obj ri_lib.obj ta.obj ta_lib.obj objects.obj ssl_compat.obj
     ```

5. **Install MSYS2 and required packages:**

   - Open MSYS2 and run the following commands:
     ```bash
     pacman -Syu
     pacman -S autoconf automake libtool make gcc pkg-config
     cd C:\projects\OpenSC-0.26.1-rc1
     ./boostrap
     cd C:\projects\OpenSC-0.26.1-rc1
     ./configure --disable-openssl --disable-readline --disable-zlib || cat config.log
     ```

6. **Modify `Make.rules.mak`:**

   - Open the file `C:\projects\OpenSC-0.26.1-rc1\win32\Make.rules.mak` in a text editor and modify the following lines:
     - Change:
       ```bash
       CNGSDK_INCL_DIR = "/IC:\Program Files (x86)\Microsoft CNG Development Kit\Include"
       ```
       to:
       ```bash
       CNGSDK_INCL_DIR = "/IC:\Program Files (x86)\Windows Kits\10\Cryptographic Provider Development Kit\Include"
       ```

     - Change:
       ```bash
       CNGSDK_INCL_DIR = "/IC:\Program Files\Microsoft CNG Development Kit\Include"
       ```
       to:
       ```bash
       CNGSDK_INCL_DIR = "/IC:\Program Files (x86)\Windows Kits\10\Cryptographic Provider Development Kit\Include"
       ```

7. **Build OpenSC:**

   - In the Developer Command Prompt, run the following commands:
     ```bash
     cd C:\projects\OpenSC-0.26.1-rc1
     nmake /f Makefile.mak OPENSSL_DEF=/DENABLE_OPENSSL OPENSSL_DIR=C:\OpenSSL-Win64 OPENSSL_EXTRA_CFLAGS=/DOPENSSL_SECURE_MALLOC_SIZE=65536 ZLIBSTATIC_DEF=/DENABLE_ZLIB_STATIC ZLIB_INCL_DIR=/IC:\zlib ZLIB_LIB=C:\zlib\zlib.lib OPENPACE_DEF=/DENABLE_OPENPACE OPENPACE_DIR=C:\openpace
     ```

   - Then, navigate to the `win32` directory and run:
     ```bash
     cd win32
     nmake /nologo /f Makefile.mak OPENSSL_DEF=/DENABLE_OPENSSL OPENSSL_DIR=C:\OpenSSL-Win64 OPENSSL_EXTRA_CFLAGS=/DOPENSSL_SECURE_MALLOC_SIZE=65536 ZLIBSTATIC_DEF=/DENABLE_ZLIB_STATIC ZLIB_INCL_DIR=/IC:\zlib ZLIB_LIB=C:\zlib\zlib.lib OPENPACE_DEF=/DENABLE_OPENPACE OPENPACE_DIR=C:\openpace OpenSC.msi
     ```

---

## Rebuild After Updating the Source Code

If you want to rebuild after updating the source code:

1. Remove file **OpenSC.msi**

2. **Open** "Developer Command Prompt for Visual Studio 2017" **as Administrator**.

3. Run the following commands:
   ```bash
   call "path_to_your_file\vcvarsall.bat" x64

   cd C:\projects\OpenSC-0.26.0-rc1
   nmake /f Makefile.mak OPENSSL_DEF=/DENABLE_OPENSSL OPENSSL_DIR=C:\OpenSSL-Win64 OPENSSL_EXTRA_CFLAGS=/DOPENSSL_SECURE_MALLOC_SIZE=65536 ZLIBSTATIC_DEF=/DENABLE_ZLIB_STATIC ZLIB_INCL_DIR=/IC:\zlib ZLIB_LIB=C:\zlib\zlib.lib OPENPACE_DEF=/DENABLE_OPENPACE OPENPACE_DIR=C:\openpace

   cd win32
   nmake /nologo /f Makefile.mak OPENSSL_DEF=/DENABLE_OPENSSL OPENSSL_DIR=C:\OpenSSL-Win64 OPENSSL_EXTRA_CFLAGS=/DOPENSSL_SECURE_MALLOC_SIZE=65536 ZLIBSTATIC_DEF=/DENABLE_ZLIB_STATIC ZLIB_INCL_DIR=/IC:\zlib ZLIB_LIB=C:\zlib\zlib.lib OPENPACE_DEF=/DENABLE_OPENPACE OPENPACE_DIR=C:\openpace OpenSC.msi
  ```
