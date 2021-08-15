# Nomenclature Project Package Name

The identifier used to name the project package





Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Format](#format)
- [Use Examples](#use-examples)





## Check Prerequisites

 * The use of CamelCase nomenclature WITHOUT separator is recommended
 * It is recommended not to use compositions → Each word is a package
 * It is recommended that this be unique
 * English is recommended





## Format

<_TYPE_> . <_COMPANY_> . <_CONTEXT / APP_> . <_MODULE_>+? . <_FEATURES_>? . <_FUNCTIONALITY_>? . (<_SUB FUNCTIONALITY_>)?+

Details

 * <_TYPE_> : fixed prefix (default com) -> can be either a country or an organization
 * <_COMPANY_> : name of the owner of the product (by default cistec)
 * <_CONTEXT/APP_> : name of the field or asset of the project
 * <_MODULE_> (optional) : Name of a module (*1)
 * <_FEATURES_> (optional development) : Name of a specific characteristic
 * <_FUNCTIONALITY_> (optional development) : typology of classes (*2)
 * <_SUB FUNCTIONALITY_> (optional development) : typology of classes (*2)

See Definitions and Acronyms

(*1) common, testing, security, core, web, report, rest, …

(*2) constant, entity, enumerate, exception, factory, repository / dao, service, validation, util, ….





## Use Examples

 * com.acme.architecture.testing
 * com.acme.architecture.persistence
 * com.acme.core
 * com.acme.web
