# Nomenclature User Group

The identifier used to identify the user groups (used in AZURE AD, ...)





Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Format](#format)
- [Use Examples](#use-examples)





## Check Prerequisites

 * The use of Upper Case nomenclature is recommended or, alternatively, the separation of words by the characters "-" or "_"
 * It is recommended that this be unique
 * English is recommended
 * The DESCRIPTION field should not contain the name of the application as it is already reflected in the COMPANY/PROJECT field





## Format

<_COMPANY_>-<_PROJECT_>-<_SCOPE_>-GROUP

Details

 * <_COMPANY_> : Text string represents the company or enterprise that is responsible for the group
    * There may be some identifier that means that it is a global instance for the whole company
 * <_PROJECT_> : Text string represents an internal code representing the project → its values may be acronyms or codes of other projects
    * When it is a resource that is common to several projects or to a company, we will put COMMON
 * <_SCOPE_> : Text string represents the context that usually corresponds to a functional unit
    * BACKEND: BACK developers of the PROJECTX
    * DEVOPS: DEVOPS Group of ACME
    * MANAGEMENT: Group of ACME Managers who want to have access
 * GROUP : represents the context that usually corresponds to group





## Use Examples

 * ACME-PROJECTX-BACKEND-GROUP
 * ACME-COMMON-DEVOPS-GROUP
 * ACME-COMMON-MANAGMENT-GROUP
