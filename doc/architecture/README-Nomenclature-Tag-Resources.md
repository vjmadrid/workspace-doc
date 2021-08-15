# Nomenclature Tag Resources

Proposal of tag categories for poor usage groups, cost, automation, security, ...

 * Take advantage of the tagging provided by the Cloud provider.
 * Facilitate access from console or API
 * Facilitates the use of templates
 * Facilitates other automations → Ansible, Chef, ...
 * Requires Tag Checker setup → Warn when tags are missing, etc,
 * General tag application proposals : Cost Centre, Owners (team, department, application), LOB, Business Unit, Public, Private, Confidentiality, Environment, Function, Project, Security, Automation, cluster, expiry date ...





Steps to define a tag strategy :

 * Define a draft of the tagging policies required in the global tags.
 * Acceptance of the naming conventions and syntax of global tags
 * Validate the above
 * Define a draft of the tagging policies required for specific tags
 * Acceptance of naming conventions and syntax for specific tags
 * Validate the above
 * Communicate the defined tag strategy
 * Set up reports on tagging coverage by ......
 * Review reports


Azure Conditions

Max of Tags : 50

Key → 512 characters (For multicloud support use only lowercase, numbers, dash → 63 characters for the key and 63 characters for the value)

Value → 256 characters


Example:

costcenter : marketing

environment : dev


Avoid other key and value values

Example

Environment : Development


Tags allow to use multiple values in a single tag → Assemble a JSON of your own

    Better to use tag composition with "|"









Step to follow:

- [Check Prerequisites](#check-prerequisites)
- [Format](#format)
- [Use Examples](#use-examples)





## <a name="check-prerequisites">Check Prerequisites</a>

 * The use of CamelCase nomenclature is recommended or, alternatively, the separation of words by the characters "-" or "_"
 * It is recommended that this be unique
 * English is recommended
 * The DESCRIPTION field should not contain the name of the application as it is already reflected in the COMPANY/PROJECT field

 * Lower case
 * English
 * No spaces
 * No Acronyms
 * Self-explanatory




## <a name="format">Format</a>

| Tag |  Descripción | Ejemplos |
|---| --- | --- |
| Environment  | Identificar el tipo de entorno | 
    env = dev
    env = test
    environment = uat
| rm_keys  | Elimina las claves ssh a las máquinas remotas |

| ssl  | Renueva los certificados para HTTPs


		

    

Application	

1 o + tags que definan la aplicación o el servicio

sobre el que aplican
	

    app = cistecapp
    srv = techservice

Billing	1 o + tags que definan o permita localizar los costes asociados	

    region =weu
    owner = jonay
    costcenter = tech
    bu = health

Optimization	1 o + tags que definan la automatizacion	

    schedule = 24x7
    off = nigth
    on =  Monday22h30m
    maxruntime = 5days

Technical	1 o + tags que definan características técnicas	

    version = 2.0
    name = core-api

Security	1 o + tags que definan características de seguridad	

    confidentiality
    compliance





## <a name="use-examples">Use Examples</a>

environment	Etiqueta que define el tipo de entorno utilizado	Cadena de Texto basada en un tipo enumerado	Environment	
	

    environment : production
    environment : qa
    environment : development
    environment : cicd

appengine
	

Etique de idenfica una aplicación técnica utilizada

Se utiliza sobre todo en los servidores de infraestructura de los proyectos / devops
	Cadena de Texto Libre	Technical	
	

    appengine : jenkins
    appengine : tomcat

service	

Etiqueta que identifica el servicio al que esta asociado el recurso

Es obligatorio su uso en recursos específicos
	Cadena de Texto Libre	Application	
	

    service : cistec (Representa el propio servicio interno)
    service : dae
    service : conor

application	

Etiqueta que identifica el servicio al que esta asociado el recurso

Es obligatorio su uso en recursos específicos de proyectos
	Cadena de Texto Libre	Application	
	

    application : dae
    application : techcare

backuppolicy	

Etiqueta para definir la estrategia de backup en base a la planificación definida por una expresión CRON

Si NO tiene etiqueta no tiene backup
	Expresion CRON	Backup	
	

    backuppolicy : 0m18hFrid (Cada día a las 18h)

costcenter	

Etique que identifica el centro de costes al que estará asociado el gasto

Obligatorio en todos los recursos
	
	Billing	
	

    costcenter : cistec
    costcenter : atsistemas
    costcenter : conor

region	Etiqueta incluida con la región	Cadena de Texto basada en los códigos de Azure	Billing	
	

    region : weu
    region : xxx

confidentiality	
	

Boolean

Grados confindencialidad
	
	
	DUDAS Genial
quarantine	Solo existe si el recurso se queda en un estado temporal hasta que un criterio lo evalue	

Único valor → true
	Operation	
	
delete	

Solo existe si el recurso se tiene que borrar en algun periodo de tiempo


	

Único valor → true
	Operation	

