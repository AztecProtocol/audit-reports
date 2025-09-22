# Issue comparison

There is a discrepancy in the grading of various issues between the vendors. In the table we grade them on the following criteria:

1. Critical. Soundness vulnerability that is likely (doesn't require a specifically constructed circuit) or a completeness issue that will DEFINITELY appear in some natural circuits
2. High. A soundness vulnerability that requires a specific circuit or a highly likely completeness issue
3. Medium. Completeness issues or extremely unlikely soundness issues that will not lead to actual vulnerabilities or APIs which should not be used. Extremely unlikely soundness issues
4. Low. Very unlikely completeness issues

The ratings are subjective and take into account the usage of APIs by the Aztec team so can be different from vendors' who may view the class in isolation. The issues deemed informational by the vendors are not covered in the table.

ZKSecurity uses a different scale to Zellic and Spearbit, the most severe rating they assign is HIGH. 

The length of the engagement was set by the teams before the engagement and so differed. ZKSecurity spent 5, while Spearbit spent 6, and Zellic spent 2.4. Zellic limited the scope to a smaller one before the end of the engagement due to time constraints [footnote: see Zellic's report, section 1.3 on pages 6 and 7]. Auditing teams consisted of 2 engineers in the case of ZKSecurity and Spearbit, and 3 in the case of Zellic.

The table contains the id in the appropriate report and the severity assigned by the vendor. 

| Issue Number       | Description                                                  | ZKSecurity        | Zellic                          | Spearbit            |
| ------------------ | ------------------------------------------------------------ | ----------------- | ------------------------------- | ------------------- |
| 1 (Critical)       | Deduplicating Cached<br/>Multiplications Leaves Outputs<br/>Unconstrained | 00. High          | Not in Scope                    | Not in scope        |
| 2 (Critical)       | Unconstrained Exponent                                       | 02. High          | Not in updated scope for Zellic | 3.1.1 Critical      |
| 3 (Critical)       | Unconstrained Limbs in Exponentiation                        | 03. High          | Not in updated scope for Zellic | 3.2.1 High          |
| 4 (High)           | Broken Bigfield Constructor for Non-Normalized Inputs        | 01. High          | 3.4 Critical                    | 3.1.2 Critical      |
| 5 (High)           | Maximum Limb Size Fails to Ensure Multiplication Soundness   | 04. Medium        | 3,1 Critical and 3.2 Critical   | 3.3.2 Medium        |
| 6 (High)           | Broken Bigfield Constructor for Fields of Odd Bitlength      | 05. Medium        | -                               | -                   |
| 7 (High)           | Swapped Range Constraints on Carries                         | 06. Medium        | -                               | 3.4.1 Low           |
| 8 (High)           | Unsafe Constructors Allow Breaking Core Invariant            | 07. Medium        | 3.5 Critical and 3.6 High       | 3.5.6 Informational |
| 9 (High)           | Underflow possible in evaluate_non_native_field_multiplication | -                 | 3.3 Critical                    | -                   |
| 10 (High)          | to_byte_array can have aliases                               | -                 | -                               | 3.3.1 Medium        |
| 11 (Medium)        | Unsound Edge Cases in Not-Equals Assertion                   | 0b. Low           | 3.7 High                        | -                   |
| 12 (Low)           | Maximum High Carry Too Small                                 | 09. Low           | -                               | -                   |
| 13 (Low)           | Equation checks not enforced                                 | -                 | 3.8 Low                         | -                   |
| 14 (Low)           | Null-pointer dereference                                     | -                 | 3.11 Low                        |                     |
| 15 (Low)           | Handling of constant exponents                               | 0a. Low           | Not in updated scope for Zellic | -                   |
| 16 (Low)           | Maximum Values Higher Than<br/>Necessary                     | 0e. Informational | 3.12 Low                        | -                   |
| 17 (Low)           | Assertion needed to prevent bypass range-checks in unsafe_evaluate_multiply_add | -                 | -                               | 3.4.2 Low           |
| 18 (Informational) | Incompleteness of Not-Equals Assertion                       | 08. Low           | -                               | -                   |
| 19 (Informational) | Large limbs for constant inputs to conditional_negate        | -                 | 3.9 Low                         | -                   |
| 20 (Informational) | Incomplete constant check                                    | -                 | 3.10 Low                        | -                   |
| 21 (Informational) | Mistakes in calculation of MAX_UNREDUCED_LIMB_SIZE           | -                 | 3.13 Low                        | -                   |
| 22 (Informational) | Behavior of assert_equal for constant operands               | -                 | 3.14 Low                        | -                   |
| 23 (Informational) | Assert for add_to_lower_limb could be ineffective due to overflow | -                 | 3.15 Low                        | -                   |