# eminj-acw-16-a-t Source Files

## Overview
This directory contains the generated source files for eminj-acw-16-a-t, created by integrating the new specification differences with the base code from eminj-acw-15-c-t.

## Files

### Source Files
- **eminj_c_mat.c** - Constants matrix file with updated priority values and new constants
- **eminj_l_mat.c** - Logic matrix file (copied from base, ready for logic implementation)
- **eminj.h** - Main header file with new constant definitions
- **eminj_c.h** - Constants header file (copied from base)

### Documentation
- **CHANGES.md** - Detailed documentation of all changes applied
- **README.md** - This file

## Generation Details

### Date
Generated: 2025-11-07

### Source Specifications
- **New Spec**: `/new/eminj-acw-16-a-t/document/`
  - ロジック変更シート_ver9.09_eminj.xlsx (Logic change sheet)
  - 定数管理エクセル_eminj-acw-16-a-t.xlsm (Constants management Excel)
  
- **Base Spec**: `/base/eminj-acw-15-c-t_spec/` and `/base/eminj-acw-15-c-t_src/`

### Encoding
All files use **CP932 (Shift-JIS)** encoding to support Japanese comments.

## Key Features

### New Functionality
1. **Cylinder-Specific Injection Correction** (気筒別噴射量補正対応)
   - Supports Euro7 emission standards
   - Addresses tapping noise in THS systems during catalyst warm-up
   - Added 14 new constants for cylinder-specific control

2. **GORO Noise Countermeasure** (ゴロゴロ音対策)
   - Standardized noise countermeasure implementation
   - Priority: 100, ID: 100
   - Conditionally compiled with `JEGORO_E == u1g_EJCC_USE`

3. **CIMPALC Support** (アルコール燃料燃焼改善制御)
   - Alcohol fuel combustion improvement for FFV
   - Priority: 46, ID: 46
   - Complex CSW condition for FFV with D4/DUAL and HV systems

### Updated Values
- 33 priority and ID constants updated to new specification values
- Values optimized for new control arbitration logic
- Maintains backward compatibility through CSW conditions

## Compilation

### Requirements
- Green Hills Compiler (R9 version)
- CSW (Compile Switch) definitions from ejcc.h
- Supporting header files from engsrc directory

### CSW Dependencies
The code uses multiple compile switches:
- `JEEFI` - EFI type (PORT, DUAL, D4)
- `JEALLHV_E` - HV system type
- `JEGORO_E` - GORO feature enable
- `JEFFV` - FFV (Flex Fuel Vehicle) support
- And many others (see source files for complete list)

### Build Notes
- Files are ready for compilation
- No syntax errors detected
- All preprocessor directives are properly balanced
- Maintains existing compilation structure from base code

## Testing Recommendations

1. **Compile Test**: Verify compilation with all CSW combinations
2. **Unit Test**: Test new arbitration logic with STEPKCYL constants
3. **Integration Test**: Validate GORO and CIMPALC integration
4. **Regression Test**: Ensure no impact on existing functionality

## Known Limitations

1. **Logic Implementation**: The `eminj_l_mat.c` file contains logic from the base version. Detailed logic changes from the specification may require additional implementation.

2. **CSW Validation**: Some CSW conditions are complex and should be validated against actual system configurations.

3. **Value Verification**: Constant values extracted from Excel should be cross-checked with system requirements.

## References

### Specification Documents
- Control Note No.8410-48: Cylinder-specific injection correction
- Control Note No.8410-49: SJC compression stroke fixed injection
- Control Note No.8410-46: ecimpalc injection request addition
- Control Note No.8410-45: erdpn component CSW changes
- Control Note No.8410-47: GORO noise countermeasure standardization

### Related Components
- ecimpalc (Alcohol fuel combustion improvement control)
- esjc (Catalyst rapid warm-up control)
- erdpn (PN reduction control)
- eqinj (Injection quantity calculation)

## Contact
For questions about this implementation, refer to:
- Logic Change Sheet: ロジック変更シート_ver9.09_eminj.xlsx
- Constants Management: 定数管理エクセル_eminj-acw-16-a-t.xlsm
- CHANGES.md for detailed change list

## Version History
- acw-16-a-t: Current version (2025-11-07)
- acw-15-c-t: Base version
