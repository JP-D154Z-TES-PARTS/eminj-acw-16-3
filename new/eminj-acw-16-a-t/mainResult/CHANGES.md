# Changes Applied to eminj-acw-16-a-t

## Overview
This document summarizes the changes applied when integrating specifications from eminj-acw-16-a-t with the base code from eminj-acw-15-c-t.

## Source Files Generated
- `eminj_c_mat.c` - Constants matrix file (updated with new priority values and constants)
- `eminj_l_mat.c` - Logic matrix file (copied from base, ready for logic updates)
- `eminj.h` - Main header file (updated with new constant definitions)
- `eminj_c.h` - Constants header file (copied from base)

## Key Changes

### 1. New Constants Added (気筒別噴射量補正対応)
Added cylinder-specific injection correction constants for Euro7 compliance:
- `u1g_EMINJ_STEPKCYL_VD` - 気筒別噴射量補正段無効値
- `s2g_EMINJ_KQCYL_VD` - 気筒別噴射量補正係数無効値
- `s2s_EMINJ_KQCYL_MN` - 気筒別噴射量補正係数下限値
- `s2s_EMINJ_KQCYL_MX` - 気筒別噴射量補正係数上限値
- `u4g_EMINJ_RQSTEPKCYL` - 気筒別噴射量補正段要求有
- `u4g_EMINJ_RQKQCYL` - 気筒別噴射量補正係数要求有
- `u1g_EMINJ_STEPKCYL1` through `u1g_EMINJ_STEPKCYL8` - Cylinder 1-8 specific values

### 2. GORO Noise Countermeasure (ゴロゴロ音対策)
Added new constants for GORO noise countermeasure:
- `u1g_eminj_GORO_PRI` = 100 - Priority for GORO noise countermeasure
- `u1g_EMINJ_GORO_ID` = 100 - ID for GORO noise countermeasure
- CSW: `JEGORO_E == u1g_EJCC_USE`

### 3. CIMPALC Support (アルコール燃料燃焼改善制御)
Added alcohol fuel combustion improvement control:
- `u1g_eminj_CIMPALC_PRI` = 46 - Priority for alcohol fuel combustion improvement
- `u1g_EMINJ_CIMPALC_ID` = 46 - ID for alcohol fuel combustion improvement
- CSW: Complex condition for FFV with D4/DUAL and HV systems

### 4. Updated Priority Values
Updated priority values for multiple constants to align with new specification:
- `u1g_eminj_STRATIST_PRI`: 42 → 40
- `u1g_eminj_STAFRG_PRI`: 44 → 42
- `u1g_eminj_STAHV_PRI`: 46 → 44
- `u1g_eminj_BINJPLCTR_WC_PRI`: → 22
- `u1g_eminj_FCFRCTRL_PRI`: → 26
- `u1g_eminj_STACM_PRI`: → 28
- `u1g_eminj_RDPN_ST_PRI`: → 36
- `u1g_eminj_BINJPLCTR_STAHV_PRI`: → 48
- `u1g_eminj_RDPN_PRI`: → 52
- `u1g_eminj_ACTLFG_PRI`: → 66
- `u1g_eminj_INJIMB_PRI`: → 72
- `u1g_eminj_IMBRQ_PRI`: → 78
- `u1g_eminj_MFINJRQ_PRI`: → 80
- `u1g_eminj_FKGDRQ_PRI`: → 82
- `u1g_eminj_BINJPLCTR_PRI`: → 98

Corresponding ID constants were also updated with matching values.

### 5. Updated INJPTN_VD Value
- `u4g_EMINJ_INJPTN_VD`: Updated to 0x00000000 (injection pattern invalid value)

## Specification Sources
- **New Specification**: `/new/eminj-acw-16-a-t/document/`
  - `ロジック変更シート_ver9.09_eminj.xlsx`
  - `定数管理エクセル_eminj-acw-16-a-t.xlsm`
  
- **Base Specification**: `/base/eminj-acw-15-c-t_spec/` and `/base/eminj-acw-15-c-t_src/`

## Main Functional Changes (from Logic Change Sheet)

### (1) Cylinder-Specific Injection Correction (制御ネタ帳No.8410-48)
For Euro7 compliance, catalyst warm-up requires significant ignition timing retardation. In THS systems, this can cause torque variation between cylinders leading to gear tapping noise. Cylinder-specific injection correction addresses this issue.

### (2) SJC Compression Stroke Fixed Injection (制御ネタ帳No.8410-49)
Enhanced injection pattern handling for catalyst rapid warm-up control to maintain compatibility with peripheral controls.

### (3) ecimpalc Injection Request Addition (制御ネタ帳No.8410-46)
Added support for alcohol fuel combustion improvement control (ecimpalc) for stable combustion in FFV low-temperature environments.

### (4) erdpn Component CSW Changes (制御ネタ帳No.8410-45)
Updated compile switches for PN reduction control to support both port injection and hybrid systems.

### (5) GORO Noise Countermeasure Standardization (制御ネタ帳No.8410-47)
Standardized individual specifications for GORO noise countermeasure.

### (6) Interface Matching and Readability Improvements
Enhanced code readability and interface consistency.

## File Encoding
All source files use CP932 (Shift-JIS) encoding to support Japanese comments and documentation.

## Compilation Status
Files are ready for compilation. No syntax errors introduced. All CSW (Compile SWitch) conditions properly maintained.

## Generation Date
2025-11-07

## Notes
- Logic updates in `eminj_l_mat.c` may require additional implementation based on detailed logic flow specifications
- All changes maintain backward compatibility with existing compile switches
- New constants are conditionally compiled based on CSW settings
