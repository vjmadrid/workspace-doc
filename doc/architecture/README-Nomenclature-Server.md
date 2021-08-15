# Nomenclature Repository

The identifier used to name the servers

Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Format](#format)
- [Use Examples](#use-examples)





## <a name="check-prerequisites">Check Prerequisites</a>

 * The use of CamelCase nomenclature is recommended or, alternatively, the separation of words by the characters "-" or "_"
 * It is recommended that this be unique
 * English is recommended
 *The description should not contain the name of the application as it is already reflected in the APP_PREFIX field





## <a name="format">Format</a>

<COMPANY>-<PROJECT>-<ENVIRONMENT>(-<INFRASTRUCTURE>-<REGION>)?-<PRODUCT/SCOPE>(-<TYPE_HW>)?

Details

 * <COMPANY> : Text string represents the company that is responsible for the machine
    * There may be some identifier that means that it is a global instance for the whole company
 * <PROJECT> : Text string represents an internal code representing the project → its values may be acronyms or codes of other projects
    * When it is a resource that is common to several projects or to a company, we will put COMMON
 * <ENVIRONMENT> (optional) : Text string represents the execution environment of the server → its values will be: DEV, CI, QA, PRE or PROD
    * DEV: development environment.
    * CI: continuous integration environment
    * QA: testing and auditing environment
    * PRE: pre-production environment
    * PROD: production environment
 * <INFRASTRUCTURE> (optional) : Text string represents the location of the infrastructure
    * AZ : Azure
    * AWS : Amazon Web Service
    * ONPREM : On Premise
    * ...
 * <REGION> (optional) : Text string represents the geographical location of the machine
    * WEU : West Europe
    * ...
 * <PRODUCT>: name of the product installed on the machine (e.g. WSO2, JENKINS).
    * Subtype (optional): subtype of the product installed on the machine (e.g. APIM).
    * Scope: represents the context that usually corresponds to a functional unit (e.g. SERVICES).
 * <TYPE_HW> (optiona) : Represents the value of its representation within the infrastructure (OPTIONAL)
    * VM : Virtual Machine
    * OSDISK : Disk
    * ...





## <a name="use-examples">Use Examples</a>

ACME-COMMON-CICD-PRE-AZ-WEU-GITLAB-VM
ACME-COMMON-CICD-PRE-AZ-WEU-JENKINS-VM
ACME-COMMON-CICD-PRE-AZ-WEU-SONAR-VM
ACME-COMMON-CICD-PRE-AZ-WEU-NEXUS-VM

ACME-GLOBAL-PRE-AZ-WEU-TOMCAT

ACME-PROJECTX-PRE-AZ-WEU-SERVICES-VM
ACME-PROJECTX-PRO-AZ-WEU-SERVICES-VM

ACME-PROJECTY-PRO-AWS-CO-SERVICES-VM