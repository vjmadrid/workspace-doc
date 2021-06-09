# Nomenclature Project Package Name

The identifier used to name the project package

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Format](#format)
- [Use Examples](#use-examples)





## <a name="check-prerequisites">Check Prerequisites</a>

 * The use of CamelCase nomenclature WITHOUT separator is recommended
 * It is recommended not to use compositions → Each word is a package
 * It is recommended to be unique
 *It is recommended to be in English





## <a name="format">Format</a>

<TYPE> . <COMPANY> . <CONTEXT / APP> . <MODULE>+? . <FEATURES>? . <FUNCTIONALITY>? . (<SUB FUNCTIONALITY>)?+

Details

 * <TYPE> : fixed prefix (default com) -> can be either a country or an organization
 * <COMPANY> : name of the owner of the product (by default cistec)
 * <CONTEXT / APP> : name of the field or asset of the project
 * <MODULE> (optional) : Name of a module (*1)
 * <FEATURES> (optional development) : Name of a specific characteristic
 * <FUNCTIONALITY> (optional development) : typology of classes (*2)
 * <SUB FUNCTIONALITY> (optional development) : typology of classes (*2)

See Definitions and Acronyms

(*1) common, testing, security, core, web, report, rest, …

(*2) constant, entity, enumerate, exception, factory, repository / dao, service, validation, util, ….





## <a name="use-examples">Use Examples</a>

com.acme.architecture.testing
com.acme.architecture.persistence
com.acme.core
com.acme.web

