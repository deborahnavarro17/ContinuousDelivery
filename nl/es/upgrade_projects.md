---

copyright:
  years: 2015, 2017
lastupdated: "2017-6-5"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Actualice su proyecto {{site.data.keyword.jazzhub_short}} a una cadena de herramientas
{: #upgrade_projects}

{{site.data.keyword.jazzhub}} está evolucionando hacia {{site.data.keyword.contdelivery_full}}. Como parte de este cambio, los proyectos se actualizarán a cadenas de herramientas.

Puede actualizar su proyecto o esperar a que se actualice automáticamente. Asegúrese de cumplir los [requisitos previos](#upgrade_prereqs) y de actualizar el proyecto lo antes posible para poder controlar el nombre de la cadena de herramientas y la organización para la que se crea.
{: shortdesc}

**Preguntas más frecuentes**

- [Mi proyecto JazzHub está asociado a la región en el Reino Unido, pero mi cadena de herramientas estará en la región EE. UU. Sur. ¿Cómo se procederá?](#faq_region)
- [¿Qué ocurrirá con mis paneles de control y elementos de trabajo en Track &amp; Plan cuando realice la actualización?](#faq_tp)
- [¿Qué ocurrirá al código del repositorio cuando realice la actualización?](#faq_repo)
- [¿Qué ocurrirá a mis definiciones de compilación en mi proyecto cuando actualice a una cadena de herramientas? ](#faq_build)
- [Necesito crear una organización para mi proyecto que se actualizará a una cadena de herramientas. 
Entiendo que necesito añadir una tarjeta de crédito a mi cuenta antes de que pueda crear una organización. ¿Se realizarán cargos en mi tarjeta de crédito? ](#faq_charges)

## Cadenas de herramientas
{: #compare_toolchains}

Las cadenas de herramientas son como proyectos, con algunas diferencias importantes:

- Los proyectos solo pueden tener un repositorio (repo) y un conducto. Las cadenas de herramientas pueden tener tantos repositorios y conductos como sea necesario.
- Las cadenas de herramientas pueden incluir herramientas que no están disponibles en proyectos, como por ejemplo Slack, Sauce Labs, PagerDuty y {{site.data.keyword.DRA_full}}.
- El acceso a las cadenas de herramientas se gestiona mediante organizaciones estándares de {{site.data.keyword.Bluemix_notm}}. La condición de miembro se mantiene a nivel de organización, a diferencia de los proyectos, donde los miembros se mantienen a nivel de proyecto.

Puede obtener información acerca de las cadenas de herramientas en [YouTube![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://youtu.be/2SIPE1e7NJ4){: new_window} o en [Iniciación a {{site.data.keyword.contdelivery_short}}](/docs/services/ContinuousDelivery/index.html).
[![Enlace externo a YouTube](images/CD_video.png)](https://youtu.be/2SIPE1e7NJ4){: new_window}

## Requisitos previos
{: #upgrade_prereqs}

- Para acceder a la cadena de herramientas actualizada del proyecto, necesita un ID de {{site.data.keyword.Bluemix_notm}}. Antes de actualizar, debe verificar que tiene un ID de {{site.data.keyword.Bluemix_notm}} activo. Si no dispone de uno, [regístrese](https://console.ng.bluemix.net/registration/).
- Asegúrese de que el propietario del proyecto de {{site.data.keyword.jazzhub_short}} sea correcto. La cadena de herramientas que se crea a partir del proyecto formará parte de la organización de {{site.data.keyword.Bluemix_notm}} de dicho propietario.
- Si está la planificación iniciar la actualización, asegúrese de que es miembro de cada organización y espacio en el que se despliega el conducto. Cualquier administrador de proyecto puede iniciar la actualización. Sin embargo, si el administrador que inicia la actualización no es miembro de cada organización y espacio en el que se despliega el conducto, no se puede crear el conducto. La persona que inicia la actualización se convierte en el propietario del repositorio en la cadena de herramientas.
- Eclipse Orion {{site.data.keyword.webide}} en la cadena de herramientas no es el {{site.data.keyword.webide}} asociado al proyecto. Si utiliza el {{site.data.keyword.webide}} y tiene cambios sin confirmar, confírmelos antes de actualizar.


## Actualización de un proyecto a una cadena de herramientas
{: #project_to_toolchain}

**Importante:** los proyectos de hub.jazz.net y de cadenas de herramientas están alojados en la región EE.UU. Sur. Si el proyecto se ha configurado para desplegar apps en otra región, seguirá desplegando apps en dicha región después de que se haya actualizado a una cadena de herramientas.

Cuando el proyecto esté listo para actualizarse, se mostrará un mensaje en la tarjeta del proyecto y en la página Visión general.

![Imagen de tarjeta con la etiqueta Preparado para actualización](images/card-project-to-upgrade.png)

![Mensaje Momento de actualizar](images/banner-ready-to-upgrade.png)

**Consejo:** Encontrará proyectos que están preparados para la actualización en el menú de la página Mis proyectos:

![Imagen del elemento de menú Proyectos para actualizar](images/menu-projects-to-upgrade.png)

Cuando inicia la actualización, las transmisiones de conducto del proyecto se bloquean. No podrá ejecutarlas ni modificarlas. Si revierte la actualización mediante la supresión de la cadena de herramientas, el conducto es desbloquea.

Si el proyecto utiliza un repositorio Git alojado en JazzHub, después de iniciar la actualización el repositorio se bloquea para garantizar la integridad de los datos que se mueven a la cadena de herramientas. Si revierte la actualización mediante la supresión de la cadena de herramientas, el repositorio de JazzHub es desbloquea.

Para ver detalles sobre cómo se trata cada tipo de repositorio en el proceso de actualización, consulte la siguiente tabla.

|Repo proyecto |Tipo proyecto	|Repo cadena de herramientas |
|:----------|:------------------------------|:------------------|
|github.com 		|Privado o público 		|El mismo repo github.com con {{site.data.keyword.Bluemix_notm}} público.	|
|hub.jazz.net/git		|Privado o público 		|Un nuevo repo en {{site.data.keyword.gitrepos}} con {{site.data.keyword.Bluemix_notm}} público.	|
{: caption="Tabla 1. Repositorios de proyecto correlacionados con repositorios de cadena de herramientas" caption-side="top"}

## Inicio del proceso de actualización
{: #start_upgrade}

Antes de iniciar el proceso de actualización, puede verlo en acción en [YouTube![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://youtu.be/LSr2e3uvyLs){: new_window}.
[![Enlace externo a YouTube](images/migration-video2.png)](https://youtu.be/LSr2e3uvyLs){: new_window}

Para actualizar el proyecto a una cadena de herramientas, siga estos pasos:

1. Para iniciar el proceso de actualización, en el mensaje de cabecera pulse **actualizar ahora**. Se abrirá la página "Cadena de herramientas de actualización de proyecto".

   ![Ejemplo de una página de actualización](images/project-upgrade-toolchain.png)

   Para obtener una visión general del proceso de actualización, lea la descripción de esta página. La cadena de herramientas incluirá un nuevo conducto que contiene las mismas etapas y trabajos que el conducto del proyecto. Además, la cadena de herramientas contendrá un puntero a Eclipse Orion {{site.data.keyword.webide}} que se ejecuta en {{site.data.keyword.contdelivery_short}}.

   En este ejemplo, como el proyecto utiliza un repositorio público en github.com, la cadena de herramientas se conectará al mismo repositorio GitHub. Si el proyecto utiliza un repositorio Git que se aloja en JazzHub, el contenido de dicho repositorio se clonará en un repositorio nuevo en {{site.data.keyword.gitrepos}}, que forma parte de {{site.data.keyword.contdelivery_short}}.

2. Para personalizar la cadena de herramientas, puede configurar algunos valores:

   - Para cambiar el nombre de la cadena de herramientas, edite el campo **Nombre**.

      ![Campo Nombre](images/name-change.png)

   - Para cambiar la organización de {{site.data.keyword.Bluemix_notm}} en la que se creará la cadena de herramientas, seleccione la organización en el menú de la cuenta:

      ![Selector de organización de Bluemix](images/bluemix-organization-chooser.png)

   Puesto que las cadenas de herramientas se gestionan a nivel de organización, asegúrese de seleccionar una organización donde los miembros del proyecto que necesiten acceder a la cadena de herramientas ya existan o se puedan añadir.

3. Si ha utilizado Track & Plan en el proyecto, puede transferir datos de Track & Plan a GitHub Issues.

   ![Opciones de Track and Plan](images/upgrade-tutorial-track-and-plan.png)

   - Indique si desea migrar los datos de Track & Plan.
   - De forma predeterminada, se migran todos los datos de Track & Plan. Si prefiere migrar solo los elementos de trabajo que forman parte de una determinada consulta, especifique la consulta.
   - Seleccione los atributos de elementos de trabajo que desea correlacionar con etiquetas en GitHub Issues.

4. Pulse **Crear**. Se crea la nueva cadena de herramientas y se muestra su página Visión general.

   ![Visión general de la cadena de herramientas actualizada](images/new-toolchain-page.png)

   - Para acceder al repositorio GitHub o al rastreador de problemas asociado, pulse **GitHub** o **Problemas**.
   - Para acceder al conducto, pulse **Conducto de entrega**.
   - Para acceder al {{site.data.keyword.webide}}, que aloja el contenido del repositorio que se ha extraído en el espacio de trabajo, pulse **Eclipse Orion {{site.data.keyword.webide}}**.

   Si vuelve al proyecto durante la actualización, el mensaje de cabecera puede indicar que la actualización está en curso, especialmente si el proceso de actualización implica importar código fuente en un repositorio nuevo o importar elementos de trabajo de Track &amp; Plan como problemas.

   ![Mensaje sobre el proyecto que se actualiza a una cadena de herramientas](images/project-being-upgraded-banner.png)

## Cómo revisitar el proyecto
{: #revisit_projects}

Está preparado para utilizar la nueva cadena de herramientas. Ahora el proyecto está etiquetado como "Actualizado" y se muestra un mensaje de configuración en la página Visión general.

![Imagen de tarjeta de proyecto con la etiqueta Actualizado](images/card-upgraded-project.png)

![Proyecto actualizado](images/banner-upgraded.png)

Puede ver los que los proyectos que se han actualizado seleccionando **Proyectos actualizados** en el menú de la página Mis proyectos:

![Imagen del elemento de menú Proyectos actualizados](images/menu-upgraded-projects.png)

Si tiene que revertir la actualización, suprima la cadena de herramientas. Puede suprimir su cadena de herramientas desde el menú **Más acciones** de la página visión general de la cadena de herramientas:

![imagen de la acción Suprimir del menú Más acciones](images/upgrade-tutorial-delete-toolchain.png)

Cuando vuelva al proyecto, se volverá a mostrar el mensaje de actualización y podrá volver a actualizar cuando esté preparado.

## Siguientes pasos
{: #upgrade_next_steps}

1. Confirme que la actualización se ha completado renovando el navegador y comprobando que aparezca el mensaje que indica que el proyecto se ha "actualizado a esta cadena de herramientas" en la página Visión general del proyecto:

   ![Mensaje de cabecera que indica que el proyecto se ha actualizado](images/banner-upgraded.png)

   **Nota:** si el mensaje indica "actualice ahora", significa que la actualización ha fallado. Pulse el enlace **actualizar ahora** para volverlo a intentar.

   ![Mensaje de cabecera que indica que el proyecto está listo para la actualización](images/banner-ready-to-upgrade.png)

2. Asigne a los miembros del equipo acceso a la cadena de herramientas.
    - Cada miembro del equipo debe tener una cuenta de {{site.data.keyword.Bluemix_notm}} válida. Los miembros del equipo que no tienen cuentas deben [registrarse ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.ng.bluemix.net/registration){:new_window}.
    - Otorgue a los miembros de la organización (org) acceso a la cadena de herramientas desde la página Gestionar de la cadena de herramientas. Para obtener más información sobre el control de accesos para cadenas de herramientas, consulte [Gestión de acceso ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](/docs/services/ContinuousDelivery/toolchains_using.html#managing_access){:new_window}.
    - Si un usuario no es miembro de la organización a la que pertenece la cadena de herramientas, añádalo a la organización desde la página Gestionar organizaciones.
      Para obtener más información sobre la gestión de organizaciones, consulte [Gestión de organizaciones y espacios ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](/docs/admin/orgs_spaces.html#orgsspacesusers){:new_window}.

3. Utilice las herramientas de la cadena de herramientas en lugar de las herramientas del proyecto de {{site.data.keyword.jazzhub_short}}. Por ejemplo, para editar código desde un navegador, utilice el IDE Web de la cadena de herramientas.

4. Si utiliza {{site.data.keyword.gitrepos}}, debe autenticarlo mediante una señal de acceso personal o una clave SSH. Para obtener más información sobre las claves SSH, consulte [Creación de una señal de acceso o clave SSH clave para la autenticación](/docs/services/ContinuousDelivery/git_working.html#git_authentication). Para autenticar desde un cliente Git externo a través de https, siga estos pasos:
    1. Vaya a la [página Señales de acceso ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://git.ng.bluemix.net/profile/personal_access_tokens){:new_window} de los valores de usuario de {{site.data.keyword.gitrepos}}.
    2. Cree una señal de acceso personal que utilice **api** como ámbito.
    3. Vaya a la [página Cuenta ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://git.ng.bluemix.net/profile/account){:new_window} y busque su nombre de usuario correspondiente a {{site.data.keyword.gitrepos}}. El nombre de usuario aparece en la lista de la sección "Cambiar nombre de usuario" y se muestra como la primera parte del URL de cualquier repositorio personal que cree.
    4. Para autenticarse con {{site.data.keyword.gitrepos}} desde un cliente Git externo a través de https, utilice su nombre de usuario y señal de acceso personal.
    5. Si desea reutilizar el repositorio local de su repositorio Git JazzHub, haga que el repositorio apunte al nuevo repositorio en {{site.data.keyword.gitrepos}}. Desde un shell de un terminal, vaya al directorio en el que se ha clonado el repositorio Git JazzHub. Escriba el mandato `git remote set-url`: `git remote set-url origin https://git.ng.bluemix.net/<id_usuario>/<nombre-nuevo-repositorio>`

        **Consejo:** para comprobar los URL definidos y sus nombres remotos, utilice el mandato `git remote -v`. El nombre remoto predeterminado es `origin`. Si tiene una configuración más avanzada, el formato del mandato es el siguiente: `git remote set-url <nombre-remoto-que-utiliza-repositorio-jazzhub> https://git.ng.bluemix.net/<id_usuario>/<nombre-nuevo-repositorio>`

5. Cuando la cadena de herramientas esté configurada y haya empezado a utilizarla, tenga en cuenta la posibilidad de llevar a cabo alguno de los siguientes pasos, o todos ellos, para asegurarse de que nadie utilice su proyecto:
    - Añada un sufijo al nombre del proyecto para indicar que no se debe utilizar. Puede añadir `_NO_UTILIZAR` al final del nombre del proyecto.
    - Actualice la descripción del proyecto para indicar que ya no se utiliza y añada un puntero a la cadena de herramientas.
    - Elimine los miembros del proyecto.
    - Cuando ya no necesite el proyecto, suprímalo.

6. Opcional: para ver la madurez del desarrollo de un proyecto, las prácticas del equipo y la calidad del código base, añada IBM Cloud {{site.data.keyword.DRA_short}} a la cadena de herramientas. {{site.data.keyword.DRA_short}} aplica analíticas de desarrollador, de equipo y de despliegue a los proyectos DevOps. Para obtener más información, consulte [Iniciación a {{site.data.keyword.DRA_short}}](/docs/services/DevOpsInsights/index.html).


## Resolución de problemas
{: #upgrade_troubleshoot}

Si tiene preguntas o detecta problemas, vaya al [foto de soporte](https://developer.ibm.com/answers/questions/ask/?smartspace=devops-services). En su publicación en el foto, incluya los URL del proyecto {{site.data.keyword.jazzhub_short}} y de la cadena de herramientas de {{site.data.keyword.contdelivery_short}} y marque la publicación con la etiqueta `devops-services`.
   
## Preguntas más frecuentes
{: #upgrade_faq}

### Mi proyecto JazzHub está asociado a la región en el Reino Unido, pero mi cadena de herramientas estará en la región EE. UU. Sur. ¿Cómo se procederá? 
{: #faq_region}

Los proyectos de hub.jazz.net y de cadenas de herramientas están alojados en la región EE.UU. Sur. Si el proyecto se ha configurado para desplegar apps en otra región, por ejemplo el Reino Unido, las apps se seguirán desplegando en dicha región después de que se haya actualizado a una cadena de herramientas. Por lo tanto, nada cambia realmente con respecto a dónde se alojan los datos. En el futuro, las cadenas de herramientas estarán disponibles en más regiones. 

### ¿Qué ocurrirá con mis paneles de control y elementos de trabajo en Track &amp; Plan cuando realice la actualización?
{: #faq_tp}

El servicio {{site.data.keyword.contdelivery_short}} proporciona funcionalidades de seguimiento de problemas a través de {{site.data.keyword.gitrepos}}, que IBM aloja y se basa en GitLab Community Edition. {{site.data.keyword.contdelivery_short}} también da soporte a las integraciones con otras herramientas de seguimiento de problemas y planificación como, por ejemplo, GitHub Issues y JIRA.

Durante el proceso de actualización, puede elegir migrar sus elementos de Track &amp; Plan a Git Issues. Tanto GitHub Issues como {{site.data.keyword.gitrepos}} proporcionan paneles kanban y seguimiento de problemas para realizar la planificación. 
Para obtener más información sobre los Paneles de problemas, una característica kanban en Git Repos and Issue Tracking, consulte [Paneles de problemas ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://git.ng.bluemix.net/help/user/project/issue_board.md){: new_window}.

Para aquellos usuarios que necesiten la misma funcionalidad que la ofrecida por JazzHub Track &amp; Plan, ahora en desuso, hay disponible el nuevo servicio IBM Track and Plan on Cloud para comprar aparte en algunos países en base a un uso por usuario y por mes. Con este servicio en la nube, obtendrá la funcionalidad completa, equivalente a la que se ofrece para licencias de contribuidor de Rational Team Concert, en una suscripción en la nube de arrendatario único. 

Este nuevo servicio IBM Track and Plan on Cloud proporciona una mayor funcionalidad que JazzHub Track &amp; Plan, ahora en desuso, dando soporte a la personalización de procesos, a jerarquías de proceso, a SAFe o a muchos otros métodos híbridos y ágiles y además ofrece la escalabilidad para crecer más allá de un proyecto individual. Se basa en la última versión de Rational Team Concert 6.0.3 y en los próximos 60 días estará en la versión 6.0.4, mientras que JazzHub Track &amp; Plan se basaba en Rational Team Concert 5.x. Es posible una migración de datos a IBM Track and Plan on Cloud a través de servicios adicionales. Puede ponerse en contacto con [Tom Hollowell ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](mailto:trhollow@us.ibm.com){:new_window}, responsable de ventas de Connected Products SaaS para obtener más información. 

Para obtener información sobre IBM Track and Plan on Cloud, o para comprar en línea, visite [IBM Marketplace ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/us-en/marketplace/cloud-change-management){: new_window}.

También es una opción comprar además software de automatización de compilaciones y gestión de código fuente, [Rational Team Concert on Cloud ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/us-en/marketplace/change-and-configuration-management/purchase#product-header-top){: new_window}.   

### ¿Qué ocurrirá al código del repositorio cuando realice la actualización?
{: #faq_repo}

Después de la actualización, el nuevo servicio Git será comparable al que tenía con anterioridad. Si utilizó github.com con sus proyectos JazzHub, su cadena de herramientas se conectará al mismo repositorio GitHub. Si su proyecto JazzHub utilizaba repositorio Git alojado en IBM, el contenido de dicho repositorio se clonará en un nuevo repositorio en {{site.data.keyword.gitrepos}}, que es parte de {{site.data.keyword.contdelivery_short}} y que IBM aloja. 

Para ver detalles sobre cómo se trata cada tipo de repositorio en el proceso de actualización, consulte la siguiente tabla.

|Repo proyecto |Tipo proyecto	|Repo cadena de herramientas |
|:----------|:------------------------------|:------------------|
|github.com 		|Privado o público 		|El mismo repo github.com con {{site.data.keyword.Bluemix_notm}} público.	|
|hub.jazz.net/git		|Privado o público 		|Un nuevo repositorio público o privado en {{site.data.keyword.gitrepos}} con {{site.data.keyword.Bluemix_notm}} público.	|
{: caption="Tabla 1. Repositorios de proyecto correlacionados con repositorios de cadena de herramientas" caption-side="top"}


### ¿Qué ocurrirá a mis definiciones de compilación en mi proyecto cuando actualice a una cadena de herramientas?
{: #faq_build}

Si está compilando su código fuente utilizando Jazz en lugar de Delivery Pipeline, debe migrar de forma manual sus definiciones de compilación a Delivery Pipeline en su cadena de herramientas.  

Si utiliza Jazz SCM como repositorio de código fuente y utiliza Delivery Pipeline para compilar su código fuente, el código fuente en Jazz SCM se moverá de forma automática a un repositorio Git. Su configuración de Delivery Pipeline permanecerá inalterada excepto que consumirá el código fuente desde el repositorio Git en lugar de hacerlo desde Jazz SCM.

### Necesito crear una organización para mi proyecto que se actualizará a una cadena de herramientas. Entiendo que necesito añadir una tarjeta de crédito a mi cuenta antes de que pueda crear una organización. ¿Se realizarán cargos en mi tarjeta de crédito? 
{: #faq_charges}

Como [cliente de Pago según uso ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud-computing/bluemix/pricing){: new_window}, si utiliza un tiempo de ejecución, servicio o componente más allá de las concesiones gratuitas que tiene en el catálogo de Bluemix, se le realizarán cargas. Para una estimación de la utilización, consulte la [hoja de cálculos de precios ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.ng.bluemix.net/?direct=classic/&cm_mc_uid=49681106114614956310454&cm_mc_sid_50200000=1495641296&cm_mc_sid_52640000=1494981898#/pricing/cloudOEPaneId=pricing&paneId=pricingSheet){: new_window}. Para conocer los precios actuales para Continuous Delivery, consulte el [catálogo de Bluemix ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://console.bluemix.net/catalog/services/continuous-delivery){: new_window}.

Si es un empleado de IBM, los proyectos internos de IBM se pueden facturar a los departamentos en lugar de hacerlo a su tarjeta de crédito personal. Si necesita recursos más allá de los asignados de forma gratuita a los empleados de IBM, cree una incidencia de soporte. 
