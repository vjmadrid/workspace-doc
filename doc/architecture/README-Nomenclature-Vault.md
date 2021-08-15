# Nomenclature Vaults

The identifier used to name the Key Vaults





Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Format](#format)
- [Use Examples](#use-examples)





## Check Prerequisites

 * The use of Upper Case nomenclature -> the separation of words by the characters "-"
 * It is recommended that this be unique
 * English is recommended





## Format

<_COMPANY/PROJECT_>-<_SCOPE_>(-<_ENVIRONMENT_>)?-KV

Details

 * <_COMPANY/PROJECT_> : Text string representing either the company or project name
    * Represents an internal code representative of the project → its values will be: ACME, UMB, ...
    * When it is a resource that is common to several projects or to a company, the same code can be used.
 * <_SCOPE_> : Text string representing the context which usually corresponds to a functional unit
    * Examples : DATA, WEB, CICD, INFRA, BUSINESS, etc
 * <_ENVIRONMENT_> (optional) : Text representing the execution environment to which it is applied
    * Facilitates the establishment of a typology of subprojects
 * KV : represents the context that usually corresponds to Key Vaults





## Use Examples

 * ACME-CICD-PRE-KV
 * ACME-CICD-PRO-KV
 * UMBRE-DATA-KV
