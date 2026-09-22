# NATProbe v4.1 Grand Slam Build Matrix

- Toolchain: `go1.23.2 linux/amd64`
- Canonical `go tool dist list` targets attempted: **49**
- Successful default targets: **44**
- Toolchain-limited targets: **5**
- Additional ISA / compatibility variants built: **44**
- Build flags: `CGO_ENABLED=0`, `-trimpath`, `-ldflags="-s -w"`.

## License / signature status

`LICENSE.md` is included exactly as supplied. The current license text literally requires a **verifiable GPG-signed** copy. This bundle does not contain a signature made by the Author, so `SIGNATURE-STATUS.txt` is included and public redistribution should wait until the Author signs the final license text.

## Default GOOS/GOARCH matrix

| GOOS | GOARCH | Build | Size | Native format | Notes |
|---|---|---:|---:|---|---|
| `aix` | `ppc64` | **OK** | 2.49 MiB | 64-bit XCOFF executable or object module not stripped | 原生 CLI 构建。 |
| `android` | `386` | **FAIL** | - | - | 当前 Linux 主机缺 Android 外部链接/NDK；Go 要求 external(cgo) linking。 |
| `android` | `amd64` | **FAIL** | - | - | 当前 Linux 主机缺 Android 外部链接/NDK；Go 要求 external(cgo) linking。 |
| `android` | `arm` | **FAIL** | - | - | 当前 Linux 主机缺 Android 外部链接/NDK；Go 要求 external(cgo) linking。 |
| `android` | `arm64` | **OK** | 2.38 MiB | ELF 64-bit LSB pie executable, ARM aarch64, version 1 (SYSV), dynamically linked, interpreter /system/bin/linker64, Go BuildID=KGKrxNDvEFFlzBSLhrsD/jJwcK2J4GsXvCaEJ689P/L1ToX7wo92BfCP6IJRjy/7089cLqrhM2SFUBZKL9H, stripped | 原生 Android ELF，可用于 shell/调试环境；不是 APK/AAB。 |
| `darwin` | `amd64` | **OK** | 2.19 MiB | Mach-O 64-bit x86_64 executable, flags:<\|DYLDLINK\|PIE> | 未做 Apple 代码签名/公证。 |
| `darwin` | `arm64` | **OK** | 2.20 MiB | Mach-O 64-bit arm64 executable, flags:<\|DYLDLINK\|PIE> | 未做 Apple 代码签名/公证。 |
| `dragonfly` | `amd64` | **OK** | 2.09 MiB | ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, Go BuildID=E6wr5cP049qDI4pSHa9_/Oq1nJmwWq1ZiQY2zlp98/WvkZmB8GpCqW_MYb8QZO/EfrAgogkX23jVH3pF3vq, stripped | 原生 CLI 构建。 |
| `freebsd` | `386` | **OK** | 1.95 MiB | ELF 32-bit LSB executable, Intel i386, version 1 (FreeBSD), statically linked, for FreeBSD 12.3, FreeBSD-style, Go BuildID=RcOsFlwlGiMfftRdBo9t/Ww7-dmTz3Xh4eMf0yfXC/kr7R-vpveScXO0HWTNZw/S0IeWIexlkiuyZIs-FVv, stripped | 原生 CLI 构建。 |
| `freebsd` | `amd64` | **OK** | 2.10 MiB | ELF 64-bit LSB executable, x86-64, version 1 (FreeBSD), statically linked, for FreeBSD 12.3, FreeBSD-style, Go BuildID=QuTyqnxdDK6WslVxikU_/drXFnjSSwzop8XNKDoHX/M_S2vlycArLOO7kjd0WX/Vm4BJrrdq29p3GvNn3xQ, stripped | 原生 CLI 构建。 |
| `freebsd` | `arm` | **OK** | 2.13 MiB | ELF 32-bit LSB executable, ARM, EABI5 version 1 (FreeBSD), statically linked, for FreeBSD 12.3, FreeBSD-style, Go BuildID=jx6GEwvaOpToTbgnQPMS/L9mytaWyWQgMEmy0eaFk/ntjTgQwOtca3jN4sD8Vj/S3LnalrpMI-9aIiXdlot, stripped | 原生 CLI 构建。 |
| `freebsd` | `arm64` | **OK** | 2.13 MiB | ELF 64-bit LSB executable, ARM aarch64, version 1 (FreeBSD), statically linked, for FreeBSD 12.3, FreeBSD-style, Go BuildID=Pn_MR_9h2RSxGq8Wr1Mw/bzFvphL10xR97JuGFs5Q/jvE62s08qFnu5Z2W7un0/yECs-FLjGN4vdPD8z2A0, stripped | 原生 CLI 构建。 |
| `freebsd` | `riscv64` | **OK** | 2.13 MiB | ELF 64-bit LSB executable, UCB RISC-V, double-float ABI, version 1 (FreeBSD), statically linked, for FreeBSD 12.3, FreeBSD-style, Go BuildID=Ju3KvfTYTALNyiNi_9mI/-UbsZ8J95BqiiEPsMlS8/fTEs-WwVuRmpHQdRxJSH/8pImFPrdqKAor5ZyRZ9D, stripped | 原生 CLI 构建。 |
| `illumos` | `amd64` | **OK** | 2.11 MiB | ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib/amd64/ld.so.1, Go BuildID=z3lgPWcMlOmgxfxptjvy/nxwRjKQJ4Gm3KeWqCjcM/OBVN6WGip6m0uyJIX6Sl/FVADimnnVY7UIjfiPFqL, stripped | 原生 CLI 构建。 |
| `ios` | `amd64` | **FAIL** | - | - | 当前 Linux 主机无 Xcode/iOS external(cgo) linking 工具链。 |
| `ios` | `arm64` | **FAIL** | - | - | 当前 Linux 主机无 Xcode/iOS external(cgo) linking 工具链。 |
| `js` | `wasm` | **OK** | 3.33 MiB | WebAssembly (wasm) binary module version 0x1 (MVP) | 可编译 WebAssembly；浏览器沙箱不提供本程序所需的原生 UDP STUN，属于编译验证/展示构建。 |
| `linux` | `386` | **OK** | 2.00 MiB | ELF 32-bit LSB executable, Intel i386, version 1 (SYSV), statically linked, Go BuildID=RsbpgzUjUZUo_MmAnddt/xi32tffQSn9JyF2wGDRZ/04UTbfmHbCQnir3fhgVW/3YWl9ME7V12PJVU1tcg3, stripped | 原生 CLI 构建。 |
| `linux` | `amd64` | **OK** | 2.12 MiB | ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, Go BuildID=RvGTY8i-TA3hOzc-o2B6/S2azj_YlX1Fjk9TJ49nb/lAA01GOwB1nwTtVOv3hI/WW15T-OqU339PAj7xK2h, stripped | 原生 CLI 构建。 |
| `linux` | `arm` | **OK** | 2.13 MiB | ELF 32-bit LSB executable, ARM, EABI5 version 1 (SYSV), statically linked, Go BuildID=m-RaDlqTPLzrWLosOvAw/-ARR_laNfaqjfX3fcUkt/5HOBjwBE99R5WUP7oBu5/NmtrMbwNZLwUFVwGUeKw, stripped | 原生 CLI 构建。 |
| `linux` | `arm64` | **OK** | 2.13 MiB | ELF 64-bit LSB executable, ARM aarch64, version 1 (SYSV), statically linked, Go BuildID=OknqBXddA8bhjuWoFNGf/P2ZrYYiEdpbWJmwECnLo/vuMD5xX7twi6AF3UtWfV/32HmSJXrZAhRAlnPenrw, stripped | 原生 CLI 构建。 |
| `linux` | `loong64` | **OK** | 2.25 MiB | ELF 64-bit LSB executable, LoongArch, version 1 (SYSV), statically linked, Go BuildID=RYvDMJBAopTg1PLniyma/VHykLf6gQsJ8fsn3YV9A/OYXy0s7783GULrA7CRPU/G6E6_cEV12cHQYT7e9_D, stripped | 原生 CLI 构建。 |
| `linux` | `mips` | **OK** | 2.44 MiB | ELF 32-bit MSB executable, MIPS, MIPS32 version 1 (SYSV), statically linked, Go BuildID=A37HJxtOv50z0YZkx65L/JJqIW_h00IysfPhKXqom/4tSP5j9cmjTbewejKUKm/CGwxaqd8jMBHBSQZ6B-Y, stripped | 原生 CLI 构建。 |
| `linux` | `mips64` | **OK** | 2.50 MiB | ELF 64-bit MSB executable, MIPS, MIPS-III version 1 (SYSV), statically linked, Go BuildID=ViUQrexQgAj6dEVRqMGM/RCtVpZ-DPi8Z4kHlbTKh/L2v2Q8E8QfZBrgC_AzC9/J2wX2C6cQBgZO__CratR, stripped | 原生 CLI 构建。 |
| `linux` | `mips64le` | **OK** | 2.50 MiB | ELF 64-bit LSB executable, MIPS, MIPS-III version 1 (SYSV), statically linked, Go BuildID=TBoCVrxi9dGQXzU8iR_m/8kjolpnYktIynBp1xVC9/9IBk6NM2spaJ7G8uEgDn/HxWPFkC0VLL6q_eNvMyc, stripped | 原生 CLI 构建。 |
| `linux` | `mipsle` | **OK** | 2.44 MiB | ELF 32-bit LSB executable, MIPS, MIPS32 version 1 (SYSV), statically linked, Go BuildID=AY3L-HKGbNpZjMxHKWag/cc8n0-dOxbcPHeTvgssR/nQkezq8yrYRC-VA7x2Q6/rXY4Ot-xAMhftVB_w0Bp, stripped | 原生 CLI 构建。 |
| `linux` | `ppc64` | **OK** | 2.19 MiB | ELF 64-bit MSB executable, 64-bit PowerPC or cisco 7500, Power ELF V1 ABI, version 1 (SYSV), statically linked, Go BuildID=hcY-rhPfLtV5VD8n2I1o/Ih8prXa0j9TE0-x3r8P_/a857YevcvIvvDodhibVV/qMOsaGJER_tLEp2kWld-, stripped | 原生 CLI 构建。 |
| `linux` | `ppc64le` | **OK** | 2.25 MiB | ELF 64-bit LSB executable, 64-bit PowerPC or cisco 7500, OpenPOWER ELF V2 ABI, version 1 (SYSV), statically linked, Go BuildID=8w1p_hitulXksikOsgW3/vBhsl2Q0P54Neo7EkMBB/aaEc4THhsYEc261REphx/CALalTu6-NzJt6rFvmFY, stripped | 原生 CLI 构建。 |
| `linux` | `riscv64` | **OK** | 2.13 MiB | ELF 64-bit LSB executable, UCB RISC-V, double-float ABI, version 1 (SYSV), statically linked, Go BuildID=y83xqZhGd6zS_qqNZSM7/m7puy5M1HJzZhtkrkzzn/hpbiEP31IT5kHnSmWPFF/9EM5y0jLSYvwfiWJdcLw, stripped | 原生 CLI 构建。 |
| `linux` | `s390x` | **OK** | 2.31 MiB | ELF 64-bit MSB executable, IBM S/390, version 1 (SYSV), statically linked, Go BuildID=-otQLrRm6FT0oAf9guWl/U7JAlfhf69lmESIFcvHg/lC64ctB3MLuc6a-1qs4b/rWEch_CaM64Yhp0BTRmW, stripped | 原生 CLI 构建。 |
| `netbsd` | `386` | **OK** | 1.93 MiB | ELF 32-bit LSB executable, Intel i386, version 1 (NetBSD), statically linked, for NetBSD 7.0, Go BuildID=fISQo9OwOqI6jRQxASjO/B-FrJUZyMk7K-7W2ex84/fUYg6XkS9ixkUMS4IAM1/Nbq-nFmnrlToUSsHlQzA, stripped | 原生 CLI 构建。 |
| `netbsd` | `amd64` | **OK** | 2.07 MiB | ELF 64-bit LSB executable, x86-64, version 1 (NetBSD), statically linked, for NetBSD 7.0, Go BuildID=XaynEMggcajKYntTQLnM/jGLFp0erRnCm4rnq3bye/rqCwX6WCc6TD7DjJ7kDw/XoayBVkf6mbZmxikzZ9c, stripped | 原生 CLI 构建。 |
| `netbsd` | `arm` | **OK** | 2.06 MiB | ELF 32-bit LSB executable, ARM, EABI5 version 1 (NetBSD), statically linked, for NetBSD 7.0, Go BuildID=akBrGgiLP7_izqwznph5/Uy8666wVs0q7dnCXR3YU/ApptYBE9wUXCvnAk1doz/TK8rTWkGl_K_DdvAIP0y, stripped | 原生 CLI 构建。 |
| `netbsd` | `arm64` | **OK** | 2.13 MiB | ELF 64-bit LSB executable, ARM aarch64, version 1 (NetBSD), statically linked, for NetBSD 7.0, Go BuildID=hGwzjlq3krVRSSP5oZHt/OPIGo24j54lqcVD-VzKB/q73GPkSwTnHg6vjFj6n8/-RHgZb3fqJ2GLc5v73Kg, stripped | 原生 CLI 构建。 |
| `openbsd` | `386` | **OK** | 1.96 MiB | ELF 32-bit LSB executable, Intel i386, version 1 (OpenBSD), dynamically linked, interpreter /usr/libexec/ld.so, for OpenBSD, Go BuildID=pAU_LXIRzztUpf0O8E5g/fTAYvtzzaGkaor3Y6-K8/hml5t-uM1nRl-wtdZvo7/hLyboQGcb_wyXjpLMoh5, stripped | 原生 CLI 构建。 |
| `openbsd` | `amd64` | **OK** | 2.11 MiB | ELF 64-bit LSB executable, x86-64, version 1 (OpenBSD), dynamically linked, interpreter /usr/libexec/ld.so, for OpenBSD, Go BuildID=nMgzpzkC-5jDJcNP24go/Lw9ca2ka5ESbNQ5pCpF2/txCVdjG-vQCuOfDw8DXh/oACPkwqN7gDHxOiYKDNk, stripped | 原生 CLI 构建。 |
| `openbsd` | `arm` | **OK** | 2.06 MiB | ELF 32-bit LSB executable, ARM, version 1 (OpenBSD), dynamically linked, interpreter /usr/libexec/ld.so, for OpenBSD, Go BuildID=cXRcu9BmYsSd5S7DX4Pg/jsY8rw9nfkZaR_8htJvo/yRzyW80-Ky4eQzS1Cjzh/OK4FUBrMPdB3yGX_pwzN, stripped | 原生 CLI 构建。 |
| `openbsd` | `arm64` | **OK** | 2.19 MiB | ELF 64-bit LSB executable, ARM aarch64, version 1 (OpenBSD), dynamically linked, interpreter /usr/libexec/ld.so, for OpenBSD, Go BuildID=T1W0_yRIxP5G-rzPh8iw/OPtIYYVhQacQcX7noVem/c3d4XzVU64LaLqJYnHcF/F_N-dTgmt2N3aWofelEH, stripped | 原生 CLI 构建。 |
| `openbsd` | `ppc64` | **OK** | 2.25 MiB | ELF 64-bit MSB executable, 64-bit PowerPC or cisco 7500, OpenPOWER ELF V2 ABI, version 1 (OpenBSD), dynamically linked, interpreter /usr/libexec/ld.so, for OpenBSD, Go BuildID=Vab9nbQDL_7OoVjjh2oj/ADcfkfPstx88OLFtD4kh/quVsDwyDKpQUA43W2xQK/ILdOMc_igQGdAooASONi, stripped | 原生 CLI 构建。 |
| `openbsd` | `riscv64` | **OK** | 2.19 MiB | ELF 64-bit LSB executable, UCB RISC-V, double-float ABI, version 1 (OpenBSD), dynamically linked, interpreter /usr/libexec/ld.so, for OpenBSD, Go BuildID=iKBfCvEsh5tkqkYCdObe/gLeZudSEXRt_Seq1-GFy/PiqrkgJ1ViFB70wV-SK3/ETbtSc-E9NHtIc-FjUr0, stripped | 原生 CLI 构建。 |
| `plan9` | `386` | **OK** | 1.74 MiB | Plan 9 executable, Intel i386 | Plan 9 原生可执行；开屏任意键会走兼容回退。 |
| `plan9` | `amd64` | **OK** | 1.85 MiB | data | Plan 9 原生可执行；开屏任意键会走兼容回退。 |
| `plan9` | `arm` | **OK** | 1.77 MiB | Plan 9 executable, ARM 7-something | Plan 9 原生可执行；开屏任意键会走兼容回退。 |
| `solaris` | `amd64` | **OK** | 2.11 MiB | ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib/amd64/ld.so.1, Go BuildID=dTNqDVXJT9UhMGZHHv_z/1CdsvEMnUQCAYEeuHg3T/v5WRzlOBqIsgsVtyCJym/I6ONtbaw7Ve_GX8sqriM, stripped | 原生 CLI 构建。 |
| `wasip1` | `wasm` | **OK** | 3.30 MiB | WebAssembly (wasm) binary module version 0x1 (MVP) | 可编译 WASI Preview 1；常规 UDP socket 能力不足，属于编译验证构建。 |
| `windows` | `386` | **OK** | 2.12 MiB | PE32 executable for MS Windows 6.01 (console), Intel i386, 6 sections | 原生 CLI 构建。 |
| `windows` | `amd64` | **OK** | 2.27 MiB | PE32+ executable for MS Windows 6.01 (console), x86-64, 8 sections | 原生 CLI 构建。 |
| `windows` | `arm` | **OK** | 2.16 MiB | PE32 executable for MS Windows 6.01 (console), ARMv7, 6 sections | 原生 CLI 构建。 |
| `windows` | `arm64` | **OK** | 2.21 MiB | PE32+ executable for MS Windows 6.01 (console), ARM64, 6 sections | 原生 CLI 构建。 |

## Extra ISA / microarchitecture variants

These are additional to the 49 canonical `GOOS/GOARCH` targets. They exercise compatibility/performance knobs that the current Go toolchain exposes.

| GOOS | GOARCH | Variant | Size | Native format |
|---|---|---|---:|---|
| `linux` | `amd64` | `goamd64-v1` | 2.12 MiB | ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, Go BuildID=RvGTY8i-TA3hOzc-o2B6/S2azj_YlX1Fjk9TJ49nb/lAA01GOwB1nwTtVOv3hI/WW15T-OqU339PAj7xK2h, stripped |
| `linux` | `amd64` | `goamd64-v2` | 2.12 MiB | ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, Go BuildID=YSXEikkLsBvMW5F9jOMj/okFRdPY1P3aYPrpeATJr/YRfPjGsJVD6N7rVGSG5w/jgnRep-GAJE_-VETJKNO, stripped |
| `linux` | `amd64` | `goamd64-v3` | 2.12 MiB | ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, Go BuildID=R_dXKvxJATaZHaMikJnl/N5J1QBz6Ja9w_LZjssWF/AMC6sBeNgCjuMaF_B2gq/Vm8EBNDC7zUroAoDj_6g, stripped |
| `linux` | `amd64` | `goamd64-v4` | 2.12 MiB | ELF 64-bit LSB executable, x86-64, version 1 (SYSV), statically linked, Go BuildID=LcNjSRG3a8kwMDkecoF5/EkcRzG6V1pVdbA94lwEe/GnTLsGHOtJoRaXYoans4/EltQah9MjS-ElN7C5myV, stripped |
| `windows` | `amd64` | `goamd64-v1` | 2.27 MiB | PE32+ executable for MS Windows 6.01 (console), x86-64, 8 sections |
| `windows` | `amd64` | `goamd64-v2` | 2.27 MiB | PE32+ executable for MS Windows 6.01 (console), x86-64, 8 sections |
| `windows` | `amd64` | `goamd64-v3` | 2.27 MiB | PE32+ executable for MS Windows 6.01 (console), x86-64, 8 sections |
| `windows` | `amd64` | `goamd64-v4` | 2.27 MiB | PE32+ executable for MS Windows 6.01 (console), x86-64, 8 sections |
| `darwin` | `amd64` | `goamd64-v1` | 2.19 MiB | Mach-O 64-bit x86_64 executable, flags:<\|DYLDLINK\|PIE> |
| `darwin` | `amd64` | `goamd64-v2` | 2.19 MiB | Mach-O 64-bit x86_64 executable, flags:<\|DYLDLINK\|PIE> |
| `darwin` | `amd64` | `goamd64-v3` | 2.18 MiB | Mach-O 64-bit x86_64 executable, flags:<\|DYLDLINK\|PIE> |
| `darwin` | `amd64` | `goamd64-v4` | 2.18 MiB | Mach-O 64-bit x86_64 executable, flags:<\|DYLDLINK\|PIE> |
| `linux` | `386` | `go386-sse2` | 2.00 MiB | ELF 32-bit LSB executable, Intel i386, version 1 (SYSV), statically linked, Go BuildID=RsbpgzUjUZUo_MmAnddt/xi32tffQSn9JyF2wGDRZ/04UTbfmHbCQnir3fhgVW/3YWl9ME7V12PJVU1tcg3, stripped |
| `linux` | `386` | `go386-softfloat` | 2.02 MiB | ELF 32-bit LSB executable, Intel i386, version 1 (SYSV), statically linked, Go BuildID=MYqDj0g_0hfMuC3v6pw7/vDDwwpESRmpd-UVYzk3i/orRHxFumQVgTuWaptULt/KJz9oY4fmZ1URr3UQUs3, stripped |
| `windows` | `386` | `go386-sse2` | 2.12 MiB | PE32 executable for MS Windows 6.01 (console), Intel i386, 6 sections |
| `windows` | `386` | `go386-softfloat` | 2.14 MiB | PE32 executable for MS Windows 6.01 (console), Intel i386, 6 sections |
| `linux` | `arm` | `goarm-5` | 2.13 MiB | ELF 32-bit LSB executable, ARM, EABI5 version 1 (SYSV), statically linked, Go BuildID=HCpC8ZGMuXPZJDWXsTuo/NIqEq78Y97TSNvJwdU9P/hHJweNJlcOX_BCriO64k/KfkrWrLD7SaAVKNlxipc, stripped |
| `linux` | `arm` | `goarm-6` | 2.13 MiB | ELF 32-bit LSB executable, ARM, EABI5 version 1 (SYSV), statically linked, Go BuildID=Ds5G7g611NdlYh0jCKLM/wDeMetBPI7q5Alh3AOTL/ksAA6-HSCKIas7eoU-FA/4pvMRIP_eNF_xg5tNdfQ, stripped |
| `linux` | `arm` | `goarm-7` | 2.13 MiB | ELF 32-bit LSB executable, ARM, EABI5 version 1 (SYSV), statically linked, Go BuildID=FsRCD2PGR9nhxTKu4zC-/EsrhV6rsQm7W8PuG0J2K/5HOBjwBE99R5WUP7oBu5/X7V7TZSh5_c8QOeZnIj9, stripped |
| `linux` | `mips` | `gomips-hardfloat` | 2.44 MiB | ELF 32-bit MSB executable, MIPS, MIPS32 version 1 (SYSV), statically linked, Go BuildID=A37HJxtOv50z0YZkx65L/JJqIW_h00IysfPhKXqom/4tSP5j9cmjTbewejKUKm/CGwxaqd8jMBHBSQZ6B-Y, stripped |
| `linux` | `mips` | `gomips-softfloat` | 2.44 MiB | ELF 32-bit MSB executable, MIPS, MIPS32 version 1 (SYSV), statically linked, Go BuildID=hOagdp5Y1g7vd26Gba39/sSS_OpRXWX8oR8hrD82T/IB0xFksE9xYKZw9Vbivk/511Fzb7i0PQBrwcwEclE, stripped |
| `linux` | `mipsle` | `gomips-hardfloat` | 2.44 MiB | ELF 32-bit LSB executable, MIPS, MIPS32 version 1 (SYSV), statically linked, Go BuildID=AY3L-HKGbNpZjMxHKWag/cc8n0-dOxbcPHeTvgssR/nQkezq8yrYRC-VA7x2Q6/rXY4Ot-xAMhftVB_w0Bp, stripped |
| `linux` | `mipsle` | `gomips-softfloat` | 2.44 MiB | ELF 32-bit LSB executable, MIPS, MIPS32 version 1 (SYSV), statically linked, Go BuildID=IXsnfu89FiWecs1tefqw/ugWkZP1Hs90Z_gP2t-sM/Xq7S1xPPQI0zryxNXtH_/wvmKzjLoqpgZJ2f8Wokn, stripped |
| `linux` | `mips64` | `gomips64-hardfloat` | 2.50 MiB | ELF 64-bit MSB executable, MIPS, MIPS-III version 1 (SYSV), statically linked, Go BuildID=ViUQrexQgAj6dEVRqMGM/RCtVpZ-DPi8Z4kHlbTKh/L2v2Q8E8QfZBrgC_AzC9/J2wX2C6cQBgZO__CratR, stripped |
| `linux` | `mips64` | `gomips64-softfloat` | 2.56 MiB | ELF 64-bit MSB executable, MIPS, MIPS-III version 1 (SYSV), statically linked, Go BuildID=9mN3l2ya9oQ-NLuVlNAg/VIeGu0o6si5Y76ZNBVkT/mm9eLWk3_MTrb91zHGc_/GvNusjuOFYBVcwP1oICG, stripped |
| `linux` | `mips64le` | `gomips64-hardfloat` | 2.50 MiB | ELF 64-bit LSB executable, MIPS, MIPS-III version 1 (SYSV), statically linked, Go BuildID=TBoCVrxi9dGQXzU8iR_m/8kjolpnYktIynBp1xVC9/9IBk6NM2spaJ7G8uEgDn/HxWPFkC0VLL6q_eNvMyc, stripped |
| `linux` | `mips64le` | `gomips64-softfloat` | 2.56 MiB | ELF 64-bit LSB executable, MIPS, MIPS-III version 1 (SYSV), statically linked, Go BuildID=OMsm9WFxkhgsOszMIJsJ/Nm3zWhV1oy4ad5ZPNdH2/j-9UnL_gDJgrPJiZ-Dek/CSm4_7FXuJDFqkm2PXU7, stripped |
| `linux` | `ppc64` | `goppc64-power8` | 2.19 MiB | ELF 64-bit MSB executable, 64-bit PowerPC or cisco 7500, Power ELF V1 ABI, version 1 (SYSV), statically linked, Go BuildID=hcY-rhPfLtV5VD8n2I1o/Ih8prXa0j9TE0-x3r8P_/a857YevcvIvvDodhibVV/qMOsaGJER_tLEp2kWld-, stripped |
| `linux` | `ppc64` | `goppc64-power9` | 2.19 MiB | ELF 64-bit MSB executable, 64-bit PowerPC or cisco 7500, Power ELF V1 ABI, version 1 (SYSV), statically linked, Go BuildID=MKPr8ocBLzWMGRvQNNIr/77u5NyrqOljU1i_jZsb4/asB29QnzPGPD2hCUmQw2/Qi47zrb77JUZgIhaS8-z, stripped |
| `linux` | `ppc64` | `goppc64-power10` | 2.25 MiB | ELF 64-bit MSB executable, 64-bit PowerPC or cisco 7500, Power ELF V1 ABI, version 1 (SYSV), statically linked, Go BuildID=78qUmnEGgaj_w-XN5rTf/SIsyBEYzulwxCk5-3R9V/WsEYzaZHhBNcCVleOo9D/EP5sq_fpqnyO_AJWVWWb, stripped |
| `linux` | `ppc64le` | `goppc64-power8` | 2.25 MiB | ELF 64-bit LSB executable, 64-bit PowerPC or cisco 7500, OpenPOWER ELF V2 ABI, version 1 (SYSV), statically linked, Go BuildID=8w1p_hitulXksikOsgW3/vBhsl2Q0P54Neo7EkMBB/aaEc4THhsYEc261REphx/CALalTu6-NzJt6rFvmFY, stripped |
| `linux` | `ppc64le` | `goppc64-power9` | 2.19 MiB | ELF 64-bit LSB executable, 64-bit PowerPC or cisco 7500, OpenPOWER ELF V2 ABI, version 1 (SYSV), statically linked, Go BuildID=3ZKdyXzpAwD3iYTU_-ep/51wLn3AdyFGFBJXdJM2C/OFa8v8W4OS6OHq9VBvhW/ChIyWXgg-ng8S2qf18sP, stripped |
| `linux` | `ppc64le` | `goppc64-power10` | 2.25 MiB | ELF 64-bit LSB executable, 64-bit PowerPC or cisco 7500, OpenPOWER ELF V2 ABI, version 1 (SYSV), statically linked, Go BuildID=R6mJk7V7I_r9TI1x1Mr_/O3gALkMve3a8inNFibgo/VhibpRbDl_jGbbCc0POy/LsGpqLMY2-bkwvIAD2lL, stripped |
| `linux` | `riscv64` | `goriscv64-rva20u64` | 2.13 MiB | ELF 64-bit LSB executable, UCB RISC-V, double-float ABI, version 1 (SYSV), statically linked, Go BuildID=y83xqZhGd6zS_qqNZSM7/m7puy5M1HJzZhtkrkzzn/hpbiEP31IT5kHnSmWPFF/9EM5y0jLSYvwfiWJdcLw, stripped |
| `linux` | `riscv64` | `goriscv64-rva22u64` | 2.13 MiB | ELF 64-bit LSB executable, UCB RISC-V, double-float ABI, version 1 (SYSV), statically linked, Go BuildID=HCK6X0dqeQHeqcTcs3ys/vV-eNV43d0RvR6Und0n-/NIIxFG6xPnRsxJxwsE66/fVCgNxRQ4odtPg7fBxnN, stripped |
| `linux` | `arm64` | `goarm64-v8.0` | 2.13 MiB | ELF 64-bit LSB executable, ARM aarch64, version 1 (SYSV), statically linked, Go BuildID=OknqBXddA8bhjuWoFNGf/P2ZrYYiEdpbWJmwECnLo/vuMD5xX7twi6AF3UtWfV/32HmSJXrZAhRAlnPenrw, stripped |
| `linux` | `arm64` | `goarm64-v8.2` | 2.13 MiB | ELF 64-bit LSB executable, ARM aarch64, version 1 (SYSV), statically linked, Go BuildID=Y7Wcl9hb-0A90TtYwfKi/NNvcNN75EGCyMQCFDI2Y/Y5cWBISlNqzu9E3m453o/5pjHQgsTay3JpuJFknMV, stripped |
| `linux` | `arm64` | `goarm64-v9.0` | 2.13 MiB | ELF 64-bit LSB executable, ARM aarch64, version 1 (SYSV), statically linked, Go BuildID=XpGxgfvK0ukN0RLbxIGI/VorY6wGLgHvzj0VQcFNb/ZiBT8WhNQfL0qJ21YCQe/6TwoDXK5pJiN1HpsbcPk, stripped |
| `windows` | `arm64` | `goarm64-v8.0` | 2.21 MiB | PE32+ executable for MS Windows 6.01 (console), ARM64, 6 sections |
| `windows` | `arm64` | `goarm64-v8.2` | 2.19 MiB | PE32+ executable for MS Windows 6.01 (console), ARM64, 6 sections |
| `windows` | `arm64` | `goarm64-v9.0` | 2.19 MiB | PE32+ executable for MS Windows 6.01 (console), ARM64, 6 sections |
| `darwin` | `arm64` | `goarm64-v8.0` | 2.20 MiB | Mach-O 64-bit arm64 executable, flags:<\|DYLDLINK\|PIE> |
| `darwin` | `arm64` | `goarm64-v8.2` | 2.18 MiB | Mach-O 64-bit arm64 executable, flags:<\|DYLDLINK\|PIE> |
| `darwin` | `arm64` | `goarm64-v9.0` | 2.18 MiB | Mach-O 64-bit arm64 executable, flags:<\|DYLDLINK\|PIE> |

## Binary/container formats represented

- **PE/COFF**: Windows 386/amd64/arm/arm64 (`.exe`).
- **ELF**: Linux, BSD family, Solaris/illumos, Android arm64 and several other Unix-like targets.
- **Mach-O**: macOS amd64/arm64.
- **XCOFF**: AIX/ppc64.
- **Plan 9 executable format**: plan9/386, plan9/amd64, plan9/arm.
- **WebAssembly**: js/wasm and wasip1/wasm.

## Packaging formats

- Per-target Windows and WebAssembly packages: ZIP.
- Per-target Unix/native packages: `tar.gz`.
- Full collection: ZIP, `tar.gz`, `tar.xz`, `tar.bz2`, and `tar.zst`.

## Runtime caveats

- The program performs real UDP STUN tests. WebAssembly browser/WASI builds compile, but their runtime environments do not expose the same UDP socket model as native operating systems.
- Android arm64 is a raw native executable, not an APK/AAB. The other Android architectures require an NDK/external linker in this Go configuration.
- iOS requires Apple external linking/signing tooling unavailable on this Linux build host, so no iOS executable is emitted.
- macOS binaries are not signed or notarized.
- The “press any key” splash is true single-key on Windows and common Unix TTYs; unusual terminals/sandboxes fall back to reading stdin and may require Enter.
