[![release][Release Badge]][Release Page]
[![license MIT][License Badge]][License Page]
 &nbsp; &nbsp; &nbsp;
[![integrated in PlantUML][Integrated Badge]][Integrated Page]
 &nbsp; &nbsp; &nbsp;
[![commits since][Commits Since Badge]][Commit Page]

[Release Badge]: https://img.shields.io/github/v/release/plantuml-stdlib/C4-PlantUML?display_name=tag
[Release Page]: https://github.com/plantuml-stdlib/C4-PlantUML/releases/v2.5.0
[License Badge]: https://img.shields.io/github/license/plantuml-stdlib/C4-PlantUML
[License Page]: https://github.com/plantuml-stdlib/C4-PlantUML/blob/master/LICENSE
[Integrated Badge]: https://img.shields.io/badge/C4--PlantUML%20%20v2.5.0%20integrated%20in%20PlantUML%20Standard%20Library-V1.2022.14-orange
[Integrated Page]: https://plantuml.com/stdlib#062f75176513a666

[Commits Since Badge]: https://img.shields.io/github/commits-since/plantuml-stdlib/C4-PlantUML/latest?label=new%20unreleased%20changes%20in%20master%20branch
[Commit Page]: https://github.com/plantuml-stdlib/C4-PlantUML/commits

# C4-PlantUML (released v2.5.0)

<span style="color: red;">This is an explicit created branch `release/v250` and therefore all following samples... uses this branch.
<br/>All (this and other) released/tagged versions can you use in your diagrams via corresponding tag-based branches too,
e.g. `!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/v2.5.0/C4_Container.puml` references tagged version `v2.5.0`)</span>

[![Container diagram for Internet Banking System](https://www.plantuml.com/plantuml/png/hLP1R-Cs4xtxLypdtOC3AF7NRdCf460TM-rcOSUkvJGz5316qbWcbY85SkGaAFhVErGKAtAss0Bj9H27dFUUdnv7-UWP7TUb7lnFcKpNES6UkV8_ZiSE7ouAnViwhJsvp1ecmnUPBSULHXDwpZtdMgNZwG_dgr2wMyp7ZZIX9py-V7_vVzdPJgKHbI5tKGMQGV9fURzTnUjaURjTtctcDxVnw6mmoVDOKoaC6on6mnIpBsJoO-ymWlSxMKojjkxgVJoF5_7jPllJKlvCb_FbMlRJudbt-Ex3XylPv3Bq-3rMT1MhOi-9oYbFmdfq9ZkQ2Y7Oq2DVlR11zaBtkw7G0Zxq31jrQzADClHF9WlGBAsjdCbwlRm_wj22yBSR2JzfkfgXtrC-LqQqzD03-FY_eR3C7SM05Mk2ev-GAomSbh2p3cuCapF4S8tcYp8594-UgHmCLkIyDQEizcnBSX5CZq_32RoKmUw0zmIfT4Vm88c1gcb4tTG0iypMXlrGT3n3Rw-baADx6cNV2TQfWE4P_340W4xlw87IBLQL7Bwd52PLfLM6hAmPIkap7Z22f791_EBNQQZDIAk3o6YaUPQp6RGP1ZHvKpxofYy_V3KHaNrcNw709RAjwNo51GNs5zOaSwhY22Qcg3MwK5uvUr0vUK2jlywogqqMfADM_0HinSd6I0y7XQ55EP3V2wcp3vxS6qMbJPMcrev5M1mrJTz5y1kMA4xqjO1MfMBAmTUf9mQx-yVQ_1jnpm8WfuFAw5JUB1tbo9YYf_0QsiUW9lbb3hqrMqSUmdG1HuNox31mWp8Iox9vZc3Vt1N0clUGESh9i4Bjen0hyXwqBMH1d5syCQgzr-AK2ebTtNmzE3ChnrpNrtFk6mu5KmIukQrO-Aitaqj4_NcCVVp88ofHwQrl2a8KdozatLwvmBpP4wY653KiLEQijpk6-37Reoa8dZi5zXLcgwr35KopSrZIoPtkR6_YsQOWamAq6A_D1qnjpLq4ekDLZe0T6e-D4vtzWpNfL-EYkxHtddpW_hJPh18vs3_dA_pccJRq7LnBjxqDepgrtOXeuBe1q28rnLuWZeJDl8tWitoHnWrvzpQRhHQXK_3lWBRNqjp9xYvB7tHDc7lOELisy-h1AIOFR0DHopExdWha4VELMoSXImJM0vs7QeFH2UdbiQ_XjA_sae-EFbbiLWBKUmUzzfDKTZvrNpcPLelvgLVTji0__xymZt-ERsUZiy57GQzB_HS0 "Container diagram for Internet Banking System")](https://www.plantuml.com/plantuml/uml/hLP1R-Cs4xtxLypdtOC3AF7NRdCf460TM-rcOSUkvJGz5316qbWcbY85SkGaAFhVErGKAtAss0Bj9H27dFUUdnv7-UWP7TUb7lnFcKpNES6UkV8_ZiSE7ouAnViwhJsvp1ecmnUPBSULHXDwpZtdMgNZwG_dgr2wMyp7ZZIX9py-V7_vVzdPJgKHbI5tKGMQGV9fURzTnUjaURjTtctcDxVnw6mmoVDOKoaC6on6mnIpBsJoO-ymWlSxMKojjkxgVJoF5_7jPllJKlvCb_FbMlRJudbt-Ex3XylPv3Bq-3rMT1MhOi-9oYbFmdfq9ZkQ2Y7Oq2DVlR11zaBtkw7G0Zxq31jrQzADClHF9WlGBAsjdCbwlRm_wj22yBSR2JzfkfgXtrC-LqQqzD03-FY_eR3C7SM05Mk2ev-GAomSbh2p3cuCapF4S8tcYp8594-UgHmCLkIyDQEizcnBSX5CZq_32RoKmUw0zmIfT4Vm88c1gcb4tTG0iypMXlrGT3n3Rw-baADx6cNV2TQfWE4P_340W4xlw87IBLQL7Bwd52PLfLM6hAmPIkap7Z22f791_EBNQQZDIAk3o6YaUPQp6RGP1ZHvKpxofYy_V3KHaNrcNw709RAjwNo51GNs5zOaSwhY22Qcg3MwK5uvUr0vUK2jlywogqqMfADM_0HinSd6I0y7XQ55EP3V2wcp3vxS6qMbJPMcrev5M1mrJTz5y1kMA4xqjO1MfMBAmTUf9mQx-yVQ_1jnpm8WfuFAw5JUB1tbo9YYf_0QsiUW9lbb3hqrMqSUmdG1HuNox31mWp8Iox9vZc3Vt1N0clUGESh9i4Bjen0hyXwqBMH1d5syCQgzr-AK2ebTtNmzE3ChnrpNrtFk6mu5KmIukQrO-Aitaqj4_NcCVVp88ofHwQrl2a8KdozatLwvmBpP4wY653KiLEQijpk6-37Reoa8dZi5zXLcgwr35KopSrZIoPtkR6_YsQOWamAq6A_D1qnjpLq4ekDLZe0T6e-D4vtzWpNfL-EYkxHtddpW_hJPh18vs3_dA_pccJRq7LnBjxqDepgrtOXeuBe1q28rnLuWZeJDl8tWitoHnWrvzpQRhHQXK_3lWBRNqjp9xYvB7tHDc7lOELisy-h1AIOFR0DHopExdWha4VELMoSXImJM0vs7QeFH2UdbiQ_XjA_sae-EFbbiLWBKUmUzzfDKTZvrNpcPLelvgLVTji0__xymZt-ERsUZiy57GQzB_HS0)

C4-PlantUML combines the benefits of [PlantUML](https://plantuml.com/) and the [C4 model](https://c4model.com/) for providing a simple way of describing and communicate software architectures – especially during up-front design sessions – with an intuitive language using open source and platform independent tools.

C4-PlantUML includes macros, stereotypes, and other goodies (like VSCode Snippets) for creating C4 diagrams with PlantUML.

- [📄 C4-PlantUML](#c4-plantuml)
  - [Getting Started](#getting-started)
    - [Including the C4-PlantUML library](#including-the-c4-plantuml-library)
    - [Now let's create a C4 Container diagram](#now-lets-create-a-c4-container-diagram)
  - [Supported Diagram Types](#supported-diagram-types)
  - [Relationship Types](#relationship-types)
  - [Layout (arrange) elements (without relationships)](#layout-arrange-elements-without-relationships)
  - [Global Layout Options](#global-layout-options)
  - [Sprites and other images](#sprites-and-other-images)
  - [Custom tags/stereotypes support and skinparam updates](#custom-tagsstereotypes-support-and-skinparam-updates)
    - [Element specific tag definitions](#element-specific-tag-definitions)
    - [Boundary specific tag definitions](#boundary-specific-tag-definitions)
    - [Comments](#comments)
    - [Sample with different tag combinations](#sample-with-different-tag-combinations)
    - [Sample with tag dependent sprites and custom legend text](#sample-with-tag-dependent-sprites-and-custom-legend-text)
    - [Sample with different boundary tag combinations](#sample-with-different-boundary-tag-combinations)
    - [Custom schema definition](#custom-schema-definition)
  - [Element and Relationship properties](#element-and-relationship-properties)
  - [Version information](#version-information)
  - [Snippets for Visual Studio Code](#snippets-for-visual-studio-code)
  - [Live Templates for IntelliJ](#live-templates-for-intellij)
    - [Prerequisites](#prerequisites)
    - [Install](#install)
    - [Usage](#usage)
  - [Advanced Samples](#advanced-samples)
    - [techtribes.js](#techtribesjs)
    - [Message Bus and Microservices](#message-bus-and-microservices)
  - [Background](#background)
  - [License](#license)
- [📄 Layout Options](LayoutOptions.md#layout-options)
- samples
  - [📄 Core Diagrams](samples/C4CoreDiagrams.md#c4-model-diagrams)

## Getting Started

### Including the C4-PlantUML library

At the top of your C4 PlantUML `.puml` file, you need to include the `C4_Context.puml`, `C4_Container.puml` or `C4_Component.puml` file found in the `root` of this repo.

To be independent of any Internet connectivity, you can download the files found in the `root` and make use of them by supplying the command line argument `-DRELATIVE_INCLUDE="."` to PlantUML:

```bash
java -jar plantuml.jar -DRELATIVE_INCLUDE="."  ...
```

> For Visual Studio Code, add the following to your settings.json:
>
> ```json
> "plantuml.jarArgs": [
>   "-DRELATIVE_INCLUDE=."
> ]
> ```

If you want to use the always up-to-date version of the C4-PlantUML library in this repo (which obviously requires an Internet connection every time you render a document), use the following:

```plantuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml
```

If you don't need the up-to-date version, PlantUML includes the last released `C4_...` files as [standard library C4](https://plantuml.com/stdlib#062f75176513a666) \(no additional files or Internet is required). You can use it with following:

```plantuml
!include <C4/C4_Container>
```

### Now let's create a C4 Container diagram

\(If you don't want run PlantUML locally you can use e.g. the [PlantUML Web Server](https://www.plantuml.com/plantuml/png/ZKzDIyH03BtFhwWzTS7jYEZ5qyfwN77nuopfD6m7qimmoIZzzquB5aKKJ-ybuNra9mf9yqZcpBEZt6Crg4QviJR1UtloEkGk2oONM96rTM6qaO1dpLQq9z_P_TNsEAzUxWys8I48YdsxlBuebzTz4O9dJ6sSOymHamHkuWAtv47Eg_e07L9To4DK7nYekaDnoIzJlJ6hIUC-sG_fCxg10uNJz8VHqoIAOoCB_3VTF29zB_nxYzNYIvsDsI7tvViF) too.)

After you have included `C4_Container.puml` you can use the defined macro definitions for the C4 elements: `Person`, `Person_Ext`, `System`, `System_Ext`, `Container`, `Relationship`, `Boundary`, and `System_Boundary`

```plantuml
@startuml C4_Elements
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

Person(personAlias, "Label", "Optional Description")
Container(containerAlias, "Label", "Technology", "Optional Description")
System(systemAlias, "Label", "Optional Description")

Rel(personAlias, containerAlias, "Label", "Optional Technology")
@enduml
```

![test](https://www.plantuml.com/plantuml/png/ZKzDIyH03BtFhwWzTS7jYEZ5qyfwN77nuopfD6m7qimmoIZzzquB5aKKJ-ybuNra9mf9yqZcpBEZt6Crg4QviJR1UtloEkGk2oONM96rTM6qaO1dpLQq9z_P_TNsEAzUxWys8I48YdsxlBuebzTz4O9dJ6sSOymHamHkuWAtv47Eg_e07L9To4DK7nYekaDnoIzJlJ6hIUC-sG_fCxg10uNJz8VHqoIAOoCB_3VTF29zB_nxYzNYIvsDsI7tvViF "test")

In addition to this, it is also possible to define a system or component boundary.

Take a look at the following sample of a C4 Container Diagram:

```plantuml
@startuml Basic Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

Person(admin, "Administrator")
System_Boundary(c1, "Sample System") {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![Basic Sample](https://www.plantuml.com/plantuml/png/JOzFJ_Cm3CRl_HHv-ruwQMlP11TEAnM20qCLxU0ufQrXaV8dYbsg2V7TSRInaOiLFx_7zhD6ae56evD_olPw743iYJpU5aMGK_wXQ3zs8qBedIMmbFVE55vB6pqBf46hhgYk5tLiRJTFHG0D4W6BpzND5IkxYerIMGYvZskI6W8wcyd1A3iNQHchGWgIN4XdIND00hExSwCTP3Xa_PAXHXglGHorT2Q-4i7lF3cReDj9xvbyWqwKtclLIrBEfjog_iz5sTJvyttBbW1YbI_5vhMAMgcrcr34W2Z82Kxd9IDcrAJYodPIH104AGEQTo6V-7qwCgEZo7DE68l92-ZVS9UpjiXEhezjMpTCHUYiNiOy025_8PRtuCnVonhiC1hz0m00 "Basic Sample")

Entities can also be decorated with icons/sprites using the $sprite parameter, for example:

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

!define DEVICONS https://raw.githubusercontent.com/tupadr3/plantuml-icon-font-sprites/master/devicons
!define FONTAWESOME https://raw.githubusercontent.com/tupadr3/plantuml-icon-font-sprites/master/font-awesome-5
!include DEVICONS/angular.puml
!include DEVICONS/java.puml
!include DEVICONS/msql_server.puml
!include FONTAWESOME/users.puml

LAYOUT_WITH_LEGEND()

Person(user, "Customer", "People that need products", $sprite="users")
Container(spa, "SPA", "angular", "The main interface that the customer interacts with", $sprite="angular")
Container(api, "API", "java", "Handles all business logic", $sprite="java")
ContainerDb(db, "Database", "Microsoft SQL", "Holds product, order and invoice information", $sprite="msql_server")

Rel(user, spa, "Uses", "https")
Rel(spa, api, "Uses", "https")
Rel_R(api, db, "Reads/Writes")
@enduml
```

![Sprites/Icons](https://www.plantuml.com/plantuml/png/hP9DZze-4CRl-HHUz3-mqaB-QhkNIfKM0UqYyK9vAUe93V40hXmxzKp2r-yuXDseBr8FFSNucNb-dcTu8eR0PMwJE-CoMsfKP-Q2tgTfW4l_PFXS7ah2a7d7wBYV-JmjBBZOqoFMrXpIuRlUCbvjPzCqe4KWfBHwy_Y_AFkXD89n6Ff5n2Ht6e_oKut6NoR3nNpz5pmk2z3XxIlNYDexIaMFYc1OQ3aGOqWrLb6Z5yh7nNmps8tNYzduduBgExWW-HnxZw_XtQPAmPrA2ytGlyhVe88_QJbzjtl2KE7FxQrfqlXsQZAT3hukjflzRh9vta_7dyRpKVS-IPPIu5qt5Zweph0azZc6ZfoNw0kBYi_0oY5gLGIloun9nF-katxer83EVVAom2uL8CthvI1wD0F6u-QCAfSIPHnZE4BMMBFSPmtsge4mr4MoRuDkJcqK54QC1yj9z8zXnUypE6sH55YhP7TIIAIiFvciRHUhsrwZGrSVf7i430SWZ4upamLF_iXg_NbQMtkhwHR3W_91Or22asTNtcGetwCFER3nhWrhxKgOoGfja_SrgoqXHVlwhoS5KQyLcU_tydvrdRr-yWf1KxgBg2W_eTEoxny0 "Sprites/Icons")

Similar to icons/sprites is it possible to add links to all elements and relationships:

```plantuml
@startuml Basic Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

Person(admin, "Administrator", $sprite="person2", $link="https://github.com/plantuml-stdlib/C4-PlantUML/blob/master/LayoutOptions.md#hide_person_sprite-or-show_person_spritesprite")
System_Boundary(c1, "Sample System", $link="https://github.com/plantuml-stdlib/C4-PlantUML") {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", $descr="Allows users to compare multiple Twitter timelines", $link="https://github.com/plantuml-stdlib/C4-PlantUML/blob/master/LayoutOptions.md")
}
System(twitter, "Twitter", $link="https://github.com/plantuml-stdlib/C4-PlantUML")

Rel(admin, web_app, "Uses", "HTTPS", $link="https://plantuml.com/link")
Rel(web_app, twitter, "Gets tweets from", "HTTPS", $link="https://plantuml.com/link")
@enduml
```

> `png` itself supports no links, therefore the following image is generated as `svg` image.
> Github does not support `svg` links in README.md.
> If you click on the image a new window is opened and there you can use the links.

![Click on the image that the links are working](//www.plantuml.com/plantuml/svg/jP9FYnD14CNlyodQMGzPIARTe1SXi3687dOrcAmUXvxfqZJsdwQgnY68tztgdOr1F8WBvf1cNdMzz-FDN1CRv27uwecBlHyig0DpffTQencRBuuFGpSGO9yYG-IcJq5dRsBPMH1RxpgzURxO5kdkzaOZU304fByjNpoJIRkHHUCYO9DBJBK5f1HdnWONvwfUbzCHe-64zLmzfOoEOLNd-tlB8daNlwxg4zV4z5UGpgTE1qCCg6_CCGtyFhDBaPfWBmxEGZibj5FW8k623cdyNPt-wyjgTnIZqBvAGxG6ZxF-IjXt9cGFQfez5hI-LDyh9RzVHSr6w5gJioHyWawjS_QkDuMz5cbpCLVhtRPvztelAmXgsLofsu-Rac-1UbpLQ-_JIAgyDbASb11a8pV3uDaLultec04Lkm1U8kc_j2or_NWeRiPJel0_P3--hghw0Fxq_PohkYEWqi_R_Nwx-zFzP7dlNqPY93xdhi-4Ru197g4Sdp65VtIzXcX5-Wa0 "Click on the image that the links are working")

Elements and relationships can be decorated with tags and explained via a calculated legend, for example:

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

AddElementTag("v1.0", $borderColor="#d73027")
AddElementTag("v1.1", $fontColor="#d73027")
AddElementTag("backup", $fontColor="orange")

AddRelTag("backup", $textColor="orange", $lineColor="orange", $lineStyle = DashedLine())

Person(user, "Customer", "People that need products")
Person(admin, "Administrator", "People that administrates the products via the new v1.1 components", $tags="v1.1")
Container(spa, "SPA", "angular", "The main interface that the customer interacts with via v1.0", $tags="v1.0")
Container(spaAdmin, "Admin SPA", "angular", "The administrator interface that the customer interacts with via new v1.1", $tags="v1.1")
Container(api, "API", "java", "Handles all business logic (incl. new v1.1 extensions)", $tags="v1.0+v1.1")
ContainerDb(db, "Database", "Microsoft SQL", "Holds product, order and invoice information")
Container(archive, "Archive", "Audit logging", "Stores 5 years", $tags="backup")

Rel(user, spa, "Uses", "https")
Rel(spa, api, "Uses", "https")
Rel_R(api, db, "Reads/Writes")
Rel(admin, spaAdmin, "Uses", "https")
Rel(spaAdmin, api, "Uses", "https")
Rel_L(api, archive, "Writes", "messages", $tags="backup")

SHOW_LEGEND()
@enduml
```

![tags](https://www.plantuml.com/plantuml/png/bLH1Rziy3BttL-ZpjuE3jN7QhIWme423f5W7f5kMjEYne2t6qIPBXYYdwxyVwIHDataRTf90FlBnKS--eWWXDfKz-i-umZOQrJB6cZvaMO2dVcdYiiaRmb1u5z75Vk6hhBRWfEQ4ehOcpqRlJwOIkh-TP04j0Y5bgxFp0MSUHrm8nc7erq9pDDJwscB5lUwWJ9FLQN-G7AitkGyQmyXR7owJ__N5ky7PHTBhG9yAUi5D_uRDeVZUr0Te7y2Lo611pz0U82F-E41oqFBqdS5vVBQeBjKOQ8bwmf6qnvsd6CYxLBPsh99HGz5N61A-Jz7NN16N49L3rAeENZT591veKmMwCewXGpaDnG3H_r8BkoGIX_2baLePQ0CEdvHiI_63rTwXYzGAX98kspKovSlJf5G3KyodGs5YYOs5blIEErKCKSP530ieDWC8Gx4Hjiw1a3-nNTe9v5Ntw0Q7TCFNEbKtCxpUmR-Ei5t07rH3RMI2wISX_0OhaFC6dBP82gnLx7m64YdhIrEeL3wH_cwrR1PqPBoZthxOjuTKuppLEJSVGuGS28NerXJ1arz4DVywQPczrRHzoMFLVX2Afs5rAsyAv7FXGmMH6VTrX69fLYXQrhT4heqsKGOlZIibCESbigvpzOmGTcROkf-DEqExSUtQ3_U499Nj7u41acyplBZkzEDilTHMx0n1K_OGJCHDUklktVjtSkpIloUQh8bsqjSy0gkG24hib3Y_-VBmEBd-UFrvdFQEhj3ffh8_0G00 "tags")

## Supported Diagram Types

> - `arg`: argument required (e.g. `alias`)
> - `?arg`: argument optional (e.g. `?tags`); an optional argument can be directly set via its keyword `$arg=...` (e.g. `$tags="specificTag"`) without the other optional arguments

- System Context & System Landscape diagrams
  - Import: `!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Context.puml`
  - Macros:
    - `Person(alias, label, ?descr, ?sprite, ?tags, ?link)`
    - `Person_Ext`
    - `System(alias, label, ?descr, ?sprite, ?tags, ?link)`
    - `SystemDb`
    - `SystemQueue`
    - `System_Ext`
    - `SystemDb_Ext`
    - `SystemQueue_Ext`
    - `Boundary(alias, label, ?type, ?tags, ?link)`
    - `Enterprise_Boundary(alias, label, ?tags, ?link)`
    - `System_Boundary`
  - Sprites:
    - `person`
    - `person2`
    - `robot`
    - `robot2`

- Container diagram
  - Import: `!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml`
  - Additional Macros:
    - `Container(alias, label, ?techn, ?descr, ?sprite, ?tags, ?link)`
    - `ContainerDb`
    - `ContainerQueue`
    - `Container_Ext`
    - `ContainerDb_Ext`
    - `ContainerQueue_Ext`
    - `Container_Boundary(alias, label, ?tags, ?link)`

- Component diagram
  - Import: `!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Component.puml`
  - Additional Macros:
    - `Component(alias, label, ?techn, ?descr, ?sprite, ?tags, ?link)`
    - `ComponentDb`
    - `ComponentQueue`
    - `Component_Ext`
    - `ComponentDb_Ext`
    - `ComponentQueue_Ext`

- Dynamic diagram
  - Import: `!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Dynamic.puml`
  - Additional Macros:
    - `RelIndex(index, from, to, label, ?tags, ?link)`
    - (lowercase) `increment($offset=1)`: increase current index (procedure which has no direct output)
    - (lowercase) `setIndex($new_index)`: set the new index (procedure which has no direct output)
    - `LastIndex()`: return the last used index (function which can be used as argument)

    following 2 macros requires V1.2020.24Beta4 (can be already tested with <https://www.plantuml.com/plantuml/>)
    - `Index($offset=1)`: returns current index and calculates next index (function which can be used as argument)
    - `SetIndex($new_index)`: returns new set index and calculates next index (function which can be used as argument)

- Deployment diagram
  - Import: `!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Deployment.puml`
  - Additional Macros:
    - `Deployment_Node(alias, label, ?type, ?descr, ?sprite, ?tags, ?link)`
    - `Node(alias, label, ?type, ?descr, ?sprite, ?tags, ?link)`: short name of Deployment_Node()
    - `Node_L(alias, label, ?type, ?descr, ?sprite, ?tags, ?link)`: left aligned Node()
    - `Node_R(alias, label, ?type, ?descr, ?sprite, ?tags, ?link)`: right aligned Node()

Take a look at each of the [C4 Model Diagram Samples](samples/C4CoreDiagrams.md).

## Relationship Types

- `Rel(from, to, label, ?techn, ?descr, ?sprite, ?tags, ?link)`
- `BiRel` (bidirectional relationship)

You can force the direction of a relationship by using:

- `Rel_U`, `Rel_Up`
- `Rel_D`, `Rel_Down`
- `Rel_L`, `Rel_Left`
- `Rel_R`, `Rel_Right`

In following sample a person uses different systems, and a group of persons which have bidirectional relationships

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml
HIDE_STEREOTYPE()

Person(a, "A")
Person(b, "B")
Person(c, "C")
Person(d, "D")
Person(e, "E")

BiRel_U(a, b, "talk with")
BiRel_R(a, c, "talk with")
BiRel_D(a, d, "talk with")
BiRel_L(a, e, "talk with")

Person(x, "X")
System(s1, "S1")
System(s2, "S2")
System(s3, "S3")
System(s4, "S4")

Rel_U(x, s1, "uses")
Rel_R(x, s2, "uses")
Rel_D(x, s3, "uses")
Rel_L(x, s4, "uses")
@enduml
```

![(unidirectional) relationship versus bidirectional relationship](https://www.plantuml.com/plantuml/png/RO_FQhD054VtFaM-h0nySHgrcwxIgD22fQ89j2iPzT98nr7cJzE-VUyr51MoFESmFwzxRRWojXFElrRMmZQmEXipw0V65Bzu7wqvsyfgK7Kl3KZZrNt71i4blTbgquYsOb6upKYTNbAcG03NeDcNVt-7fOpm8MybA6-WppmznqbP79CyUJs-PucxSPmCbEwbo_-lre_hpHzMY8S9QyHemWOndX0G4qJdqEOWoXEDqO3XudDrmP_0TaqvfVfcYYarDrDA2HPfElmR_HjoyQCDTAxU8HUxcV19-3CHa0Xc8YGHqkPuFasECrQ3HdizdAI_bF4eWwLCHnbESW-oiPtu1G00 "(unidirectional) relationship versus bidirectional relationship")

## Layout (arrange) elements (without relationships)

In rare cases, you can force the layout of elements which have no relationships by using:

- `Lay_U(from, to)`, `Lay_Up(from, to)`
- `Lay_D(from, to)`, `Lay_Down(from, to)`
- `Lay_L(from, to)`, `Lay_Left(from, to)`
- `Lay_R(from, to)`, `Lay_Right(from, to)`

In following sample a person uses different systems, and a group of persons which have no relationships

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml
HIDE_STEREOTYPE()

Person(a, "A")
Person(b, "B")
Person(c, "C")
Person(d, "D")
Person(e, "E")

Lay_U(a, b)
Lay_R(a, c)
Lay_D(a, d)
Lay_L(a, e)

Person(x, "X")
System(s1, "S1")
System(s2, "S2")
System(s3, "S3")
System(s4, "S4")

Rel_U(x, s1, "uses")
Rel_R(x, s2, "uses")
Rel_D(x, s3, "uses")
Rel_L(x, s4, "uses")
@enduml
```

![Relationship versus Layout](https://www.plantuml.com/plantuml/png/LOvFJuD044VlV8hQ4oIMjO0NJrKWqGGZWPBeYImmiIJBGlQFsc_l34q3lRttoFw6WpPS6Ji8vwwNhR0TR4x6JFg9CSL__U_Ud6nZDQXsb0QayTjnO9FWajxijEb4tx0uskMKglUCAH30DMZs4pm-u9SwneUybw3yYSwylYLfNHxJ8lquVkMfwpbE3agFqkNtc-tprhjgW_goQ8iQBzgX9ei2QehgPFnSLpJLU3CNnEs54-BkmXanBCV_SE0J1ygpDZ2uUezUxbSXe12iGaWXN8M8GaG_KO2eAvgSPwm6ZPLYCSVWDYPp36zZDiTeYGUGdHt4Fm00 "Relationship versus Layout")

(In combination with [SHOW_FLOATING_LEGEND()](LayoutOptions.md#show_floating_legend)) a greater distance between an element and the
e.g. floating legend could be required that all e.g. corners of the drawing area can be reached.

- `Lay_Distance(from, to, ?distance)`: Sets the distance between `from` and `to` with down alignment (Lay_Distance(from,to,0) equals Lay_D(from, to)). The default alias of the floating legend is LEGEND().

In following sample the floating legend should be in the left bottom corner of the drawing are.
(The normal SHOW_LEGEND() call requires no extra Lay_Distance() call and the legend is automatically drawn below the diagram on the right side)

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

!define DEVICONS https://raw.githubusercontent.com/tupadr3/plantuml-icon-font-sprites/master/devicons
!define FONTAWESOME https://raw.githubusercontent.com/tupadr3/plantuml-icon-font-sprites/master/font-awesome-5
!include DEVICONS/angular.puml
!include DEVICONS/java.puml
!include DEVICONS/msql_server.puml
!include FONTAWESOME/users.puml

Person(user, "Customer", "People that need products", $sprite="users")
Container(spa, "SPA", "angular", "The main interface that the customer interacts with", $sprite="angular")
Container(api, "API", "java", "Handles all business logic", $sprite="java")
ContainerDb(db, "Database", "Microsoft SQL", "Holds product, order and invoice information", $sprite="msql_server")

Rel(user, spa, "Uses")
Rel(spa, api, "Uses")
Rel_R(api, db, "Reads/Writes")

SHOW_FLOATING_LEGEND()
Lay_Distance(LEGEND(), db, 1)
@enduml
```

![db below legend, 1 unit distance](https://www.plantuml.com/plantuml/png/hL5DRzf04BtxLsnG3o05t8_cKgbI4904YGyAf1ojmJl0LkjTTsSCwh_lB9Z4QbMfXvoyVZFpthmtzyGGk2fiScDSRYkDwi1SqfSq3N3gxGqVgcr567Bl61ttSb-afGKNPxh4sffjElZSNKJeUJf90re4GagF7-_UIoKRo20OXw5NHfdaHkDEVjLmz7qycCzM_w77LGawV7hLDLBjxgIZIsKmB6e546D8DHvZZLvK7kQpTNypMisdepSLEcDmGl85TkzUmxkwIi7jAmkrwR_BF-08_weLzDDcXE68VuuttAHnTwepNSZJktQ4RbLhK17BMg4bxmNwqgBY0x1oY5gLmUigPvBYkukdhwqpLQkJl9ogJIN8y6hHZnorbVXS7r0LqgACOmmxo6jg5ZolPIyr40rrafIRGbUcfXIKHeZxYt7aZx74xnCuRP4KMAlaIj98fApVcxn95xkRNCDjMszbUWWCMo2CJ5EJ1qz-nshrRNAczbRJDOPRvOEMbKLErZvwawDyTpuKmCQxfbZZAgAPBD7MUL-oUYOamIDy1gAj9fejBqxF2ouHDAMRI4oHRFKqtsGFatb_FPuzPfFHusWsR7UI2VpAXeOON8xjAtgX-D19xj5fkVvl "db below legend, 1 unit distance")

## Global Layout Options

C4-PlantUML also comes with some layout options to make it easy and reusable to create nice and useful diagrams:

- [LAYOUT_TOP_DOWN() or LAYOUT_LEFT_RIGHT() or LAYOUT_LANDSCAPE()](LayoutOptions.md#layout_top_down-or-layout_left_right-or-layout_landscape)
- [LAYOUT_WITH_LEGEND() or SHOW_LEGEND(?hideStereotype, ?details)](LayoutOptions.md#layout_with_legend-or-show_legend)
- [SHOW_FLOATING_LEGEND(?alias, ?hideStereotype, ?details) and LEGEND()](LayoutOptions.md#show_floating_legendalias-hidestereotype-and-legend)
- [LAYOUT_AS_SKETCH() and SET_SKETCH_STYLE(?bgColor, ?fontColor, ?warningColor, ?fontName, ?footerWarning, ?footerText)](LayoutOptions.md#layout_as_sketch)
- [HIDE_STEREOTYPE()](LayoutOptions.md#hide_stereotype)

C4-PlantUML also comes with some person sprite/portrait options:

- [HIDE_PERSON_SPRITE()](LayoutOptions.md#hide_person_sprite)
- [SHOW_PERSON_SPRITE(?sprite)](LayoutOptions.md#show_person_sprite)
- [SHOW_PERSON_PORTRAIT()](LayoutOptions.md#show_person_portrait)
- [SHOW_PERSON_OUTLINE()](LayoutOptions.md#show_person_outline) (requires PlantUML version >= 1.2021.4)

## Sprites and other images

C4-PlantUML offers predefined person and robot sprites which can be directly used:

- `person`,`person2`
- `robot`, `robot2`

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Component.puml

Person(pB, "Sam", $sprite="person2")
Person_Ext(pA, "Bob", $sprite="person")

System_Ext(robB, "Robot A", $sprite="robot2")
System_Ext(robA, "Robot B", $sprite="robot")

SHOW_LEGEND()
@enduml
```

![Predefined person and robot sprites](https://www.plantuml.com/plantuml/png/PSzFIyD040NmUpv531vIQBjIz288JMhGGzLY4OzXDnbiO7TdcPduvzkx6qIKNEVztbjsow99HcUpiy5tTkmXFua4lbQAzCVwRP3JQ4O6wj0BU5btw5ImsgVEYgMtWr6xozKXdLuUzeh0WcPWzRwvkeX9kqCNqATgICza1o16NuPwcHT7xOfbViw11e6R8apHfbZyeBRvb39K4TPevZ2wxFZ50cw2X2PjFgD1oQk_dD8fpVxNrQ-kPthQldzwRVVDNVDuMowoBVW-Vk0R "Predefined person and robot sprites")

Additional `$sprite` (images) can be defined with following PlantUML supported options:

- included (standard library) sprites via their `{SpriteName}`; details see [sprites](https://plantuml.com/sprite)
- images via `img:{File or Url}`
- OpenIconic via `&{OpenIconicName}`; details see [openiconic](https://plantuml.com/openiconic)

Size of the displayed images can be changed with `,scale={factor}`.
Color of the displayed images can be changed with `,color={color}`.

(If sprites are defined via $tags then the calculated legend is updated too)

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

'stdlib users.puml defines sprite "users"
!include <office/users/users.puml>


AddRelTag("plantuml", $textColor="$ARROW_COLOR", $lineColor="$ARROW_COLOR", $sprite="img:http://plantuml.com/logo3.png{scale=0.3}", $legendSprite="img:http://plantuml.com/logo3.png{scale=0.1}", $legendText="console triggered")

Person(user, "user group displayed with a sprite", $sprite="users")


Container(container, "Container with scaled and colored OpenIconic", $sprite="&folder,scale=5.0,color=gray")

System(system, "System with an image", $sprite="img:http://plantuml.com/logo3.png")

Rel(user, system, "Rel with image (via tags)", $tags="plantuml")
Rel(user, container, "Rel with OpenIconinc", $sprite="&folder")

SHOW_LEGEND()
@enduml
```

![Sprite, image and OpenIconic](https://www.plantuml.com/plantuml/png/bP9FRnCn4CNl_XJ6gc0ZfUj0wILYKQjG0L8WrRQ8O-NQ4yUIrrxPtfO8yTtndv3T0ptabCcCtc_clVML3yo5eTFebJ9S3mBmBeJUBobrxBcMAko6ny63uzO4CA7cjgEzPYPfpdqGMZtIrVlpszJwyMrD7MXW7ZnzUdUvY9E7LHGoPS3LVLg3tXGHJb2VUrZ0LXdmsFTE1S0aZyXuqGUxtIeEDFVfAFo84BeMeWLzpsH5_fr5vlWimA-mijgwXfnTj-tcvyDgizwqQQILWHT6vO26g4ukKmnBUlIQZMihxKNT6_dRSwQXMTGNVp8I91XnTxBwxKHz7ozk2BV6MmquE2KbE11aXj0jE6zDbOpFIpfOEZlqM2WVD-n1u6SLTfWT4fnOALac23f-Y8gNAjEEtOB8bmdCZC0yPHJhJG_cQvGeFkM-tbej8g5OkQmNSvupbOxjqxgxlG_GLJx_n3tb_-5EWrN799mKUOAse0yf7BcnLQ2PYAidnN1WqiyIF1ND-2vc4y2OmSWOhPh_USssliJtihxvVFFzKpL3Ls141Fy5 "Sprite, image and OpenIconic")

Relationship specific sprites are typically smaller and therefore following options are possible:

- use smaller icons (like the $triangle in the following sample)
- use an additional scale factor (direct as part of the argument, or via a variable)
- if sprite argument starts with `&` an OpenIconic name can be used too (details see <https://useiconic.com/open>)

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Context.puml

Person(user, "User")
Person(user1, "User 1")
Person(user2, "User 2")
Person(user3, "User 3")

System(system, "System")

' normal sprites are too big 
Rel_L(user, user2, "informs", "courier", "normal sprites are too big", $sprite="person2")

' scaled sprites are ok
Rel_R(user, user3, "informs", "courier", "scaled sprites are OK", $sprite="person2,scale=0.5")

' combine sprite and scale to a new sprite
!$combinedSprite="person2,scale=0.5"
Rel_R(user, user3, "informs", "courier", "combined sprites are OK", $sprite=$combinedSprite)

' special smaller sprites can be used
sprite $triangle {
    00000000000
    00000F00000
    0000FBF0000
    0000FBF0000
    000F999F000
    000F999F000
    00F66666F00
    00F66666F00
    0F3333333F0
    0F3333333F0
    0FFFFFFFFF0
    00000000000
}
Rel_R(user1, system, "orders", "http", "small sprites, like the small triangle", $sprite="triangle")

' if sprite starts with &, sprite defines a OpenIconic, details see https://useiconic.com/open/
Rel_D(user, user1, "requests", "async message", "if sprite starts with &, it defines a OpenIconic like &envelope-closed", $sprite = "&envelope-closed")
@enduml
```

![Relationship with sprite or OpenIconic](https://www.plantuml.com/plantuml/png/bLJTQXiz4BtVfvWOaoy1s-lONmek649J5afJ4X9o7MHfR8jefQr66pUKldlrOyLsuorqRhHpHgDpT1Zj5JbcNLkhuaHghbg1i7QkeOzbQTbcj99ktIvQGikDTgZTY9kwR1JJeMT8JYYvAA__7zu5wF7RJMbH8IEaycLoEVQLf-lG-CEDca1ItA4bey_2YGFeFVgbTxuFNcnHk3Z49ncV7EBJZ4yzNZoyaiFwZEBYAoaFbVz06rip1THOwP20MGHd32pa2efxL4ytMr6PJUgbxw2U_-IcjH9j-Em-nLVx2PxtcYXmaeY9CuNYeCKyHyhxFSff9-MH_jklHzW6SUDyFBfClDpK2wbnsmXCYoG5d0466ZVRId7ItsuL3vqd_eFUV5YtuZ_uaaiDSXcSzVOgj6_Dd6bOOA0KHSAWxwnaUgKGVXRWOxoBNLuTvjMdwczvDPlDgkwy-X2YwighQOggAyynVgVtLp8sp_xRv1ehq4PdmtCCQpGcsp809PyHt1eXuTcI_Rd8M1e7kSoJ49yymKQwDPmECYfmAJKICBXjK7_XHai-yAXZKX4GxduCNgkCvVWpC7vt6M_nUJSUyHrR_DuYkNWBHg-QGur4R8K1w9GZtL4fwSAdg5zGUSeXLuPGxAuBS-YzgvuNLwX5MwlV "Relationship with sprite or OpenIconic")

## Custom tags/stereotypes support and skinparam updates

Additional tags/stereotypes can be added to the existing element stereotypes (component, ...) and highlight,... specific aspects:

- `AddElementTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?techn, ?legendText, ?legendSprite)`:
  Introduces a new element tag. The styles of the tagged elements are updated and the tag is displayed in the calculated legend.
- `AddRelTag(tagStereo, ?textColor, ?lineColor, ?lineStyle, ?sprite, ?techn, ?legendText, ?legendSprite, ?lineThickness)`:
  Introduces a new Relationship tag. The styles of the tagged relationships are updated and the tag is displayed in the calculated legend.
- `AddBoundaryTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?type, ?legendText)`:
  Introduces a new Boundary tag. The styles of the tagged boundaries are updated and the tag is displayed in the calculated legend.
- `UpdateElementStyle(elementName, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?techn, ?legendText, ?legendSprite)`:
  This call updates the default style of the elements (component, ...) and creates no additional legend entry.
- `UpdateRelStyle(textColor, lineColor)`:
  This call updates the default relationship colors and creates no additional legend entry.
- `UpdateBoundaryStyle(?elementName, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?type, ?legendText)`:
  This call updates the default style of the existing boundaries and creates no additional legend entry.
  If the element name is "" then it updates generic, enterprise, system and container boundary style in on call.
- `RoundedBoxShape()`: This call returns the name of the rounded box shape and can be used as ?shape argument.
- `EightSidedShape()`: This call returns the name of the eight sided shape and can be used as ?shape argument.
- `DashedLine()`: This call returns the name of the dashed line and can be used as ?lineStyle argument.
- `DottedLine()`: This call returns the name of the dotted line and can be used as ?lineStyle argument.
- `BoldLine()`: This call returns the name of the bold line and can be used as ?lineStyle argument.

Each element can be extended with one or multiple custom tags via the keyword argument `$tags="..."`, like `Container(spaAdmin, "Admin SPA", $tags="v1.1")`.
Multiple tags can be combined with `+`, like `Container(api, "API", $tags="v1.0+v1.1")`.

### Element specific tag definitions

Sometimes an added element tag is element specific and all element specific colors should be used, e.g. a specific user role should be defined as element tag with the specific colors `...PERSON_...` like

```plantuml
AddElementTag("admin", $fontColor=$ELEMENT_FONT_COLOR, $bgColor=$PERSON_BG_COLOR, $borderColor=$PERSON_BORDER_COLOR, $sprite="osa_user_audit", $legendText="administration user")
```

Therefore element Add...Tag() shortcuts are added which use the specific colors as default values and the call can be simplified like

```plantuml
AddPersonTag("admin", $sprite="osa_user_audit", $legendText="administration user")
```

Following calls introduces new element tags with element specific default colors:

- `AddPersonTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?legendText, ?legendSprite)`
- `AddExternalPersonTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?legendText, ?legendSprite)`
- `AddSystemTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?legendText, ?legendSprite)`
- `AddExternalSystemTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?legendText, ?legendSprite)`
- `AddComponentTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?techn, ?legendText, ?legendSprite)`
- `AddExternalComponentTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?techn, ?legendText, ?legendSprite)`
- `AddContainerTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?techn, ?legendText, ?legendSprite)`
- `AddExternalContainerTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?techn, ?sprite, ?legendText, ?legendSprite)`
- `AddNodeTag(tagStereo, ?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?sprite, ?techn, ?legendText, ?legendSprite)`
  (node specific: $type reuses $techn definition of $tags)

### Boundary specific tag definitions

Like the element specific tag definitions exist boundary specific calls with their default colors **and type**:

- `UpdateContainerBoundaryStyle(?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?type, ?legendText)`
- `UpdateSystemBoundaryStyle(?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?type, ?legendText)`
- `UpdateEnterpriseBoundaryStyle(?bgColor, ?fontColor, ?borderColor, ?shadowing, ?shape, ?type, ?legendText)`

### Comments

- `SHOW_LEGEND()` supports the customized stereotypes  
  (`LAYOUT_WITH_LEGEND()` cannot be used, if the custom tags/stereotypes should be displayed in the legend).
- `SHOW_LEGEND()` has to be last line in diagram.
- Don't use space between `$tags` and `=` (PlantUML does not support it).
- Don't use `,` as part of the tag names (PlantUML does not support it in combination with keyword arguments).
- If 2 tags define the same skinparam, the first definition is used.
- If specific skinparams have to be merged (e.g. 2 tags change the font color) an additional combined tag has to be defined. Use `&` as part of combined tag names.

- Automatically merging colors of relationship tags is not supported in PlantUML before v.1.2022  
  If an older version is used and one tag modifies the line color and the other the text color, an additional combined tag has to be defined and used.

### Sample with different tag combinations

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

UpdateElementStyle(person, $fontColor="green")
AddElementTag("v1.0", $fontColor="#d73027", $borderColor="#d73027")
AddElementTag("v1.1", $fontColor="#ffffbf", $borderColor="#ffffbf")
AddElementTag("v1.0&v1.1", $fontColor="#fdae61", $borderColor="#fdae61")
AddElementTag("fallback", $bgColor="#444444")

' If spaces are requested in the legend, legend text with space has to be defined (incl. all other additional details)
AddElementTag("microService", $shape=EightSidedShape(), $legendText="micro service (eight sided) (no text, no back color)")
' If no special tag names should be displayed in legend, no explicit legend text definition is required (all additional details are automatically calculated) 
AddElementTag("storage", $shape=RoundedBoxShape())

UpdateRelStyle(black, black)
AddRelTag("service1", $textColor="red")
AddRelTag("service2", $lineColor="red")
AddRelTag("service1&service2", $textColor="red", $lineColor="red")

Container(spa, "SPA", "angular", "The main interface that the customer interacts with via v1.0", $tags="v1.0")
Container(spaAdmin, "Admin SPA", "angular", "The administrator interface that the customer interacts with via new v1.1", $tags="v1.1")
Container(api, "API", "java", "Handles all business logic (incl. new v1.1 extensions)", $tags="v1.0&v1.1+v1.0+v1.1")
Container(spa2, "SPA2", "angular", "The main interface that the customer interacts with via v1.0", $tags="v1.0+fallback")
Container(spaAdmin2, "Admin SPA2", "angular", "The administrator interface that the customer interacts with via new v1.1", $tags="fallback+v1.1")

Container(services, "Services", "techn", $tags="microService")
Container(fileStorage, "File storage", "techn", $tags="storage")

Rel(spa, api, "Uses", "https")
Rel(spaAdmin, api, "Uses", "https")
Rel_L(spa, spa2, "Updates", "https")
Rel_R(spaAdmin, spaAdmin2, "Updates", "https")

Rel_D(api, services, "uses service1 via this call", $tags="service1")
Rel_D(api, services, "uses service2 via this call", $tags="service2")
Rel_D(services, fileStorage, "both services stores via this call", $tags="service1&service2+service1+service2")

SHOW_LEGEND(false)
@enduml
```

![merged tags](https://www.plantuml.com/plantuml/png/jLLHR-Cs37xFh-2ouPOWkUJYtNR0W0BNzRhT0TrMD2tsMD0MOskJ9K-Kq_RVZxBYmZbdA_PmVeXayUD7yZEflEU0FhIrcNobRM5QHL25qF2FwxN7XrMfGzNcBPCld0ramwfmzRenQAFFQmxAw7nzyVRrTJow-_LgxSaGCl5wdtt_HYpt5-A8sf9VDJ7CvAvH6EZIK2rqs_1aQDQGPsUNyCrEi1VEE7ysBJsHdSudvqeTiBTOpgRxpUhDz1ZvjNhttPliNJpDdLVaZyzFScm-vzZ9a-_67EdyT1wlJX8ff1ysOw9qFYRQeJ4v5dzr7cMFVjizWfvy2vzsm0qMn82UmDFVBN4W1Tf2g0WCbMJLyh12eCS03pfKoGagP0WESW95Est5RnO_z0eaBZWXy81AwQ2THIEOWDhmACjQ5zvjoUzrGJ5Jhh2XiqjTLc6h5QbjV9_DnPBIk9Kipf8NS7A36KKuSCJFOMPTb-iIP1C5W2BMFf_EKybooWqL6Wq4BC5YJGnSkTQehXZDZS6d94ClWVZGOsDqeSDGZbHvLo9exXJKFWeX4eoBJp9Z6roDGHU2UGBvBLg38IR-kJGSdCToeCgDQwsK-9DxFAWoxvl-Xang-Dn8mKlebavhiIIof5NNFv9wtrMIxVGKBeiueoszWDkywXt6n2Sf9izJE-C6bp3TNfzFPK5RYWu-RcyhWbeWe6qWlukz5YeCNKyMBOjyv9CDYy2f9VSQeP_WW2MVfNcU7uSxLxMs4g5RuNHaZ3RDmQF8_tzJiFG0QNO7QMoEqi16nmokFyM0V-8Uu_eHhJB4tUZaBGkG6OmhTT4FLSyC8Z5Prixo_2XAkZGMSRSO1PNQiwHrziN4NlGNpadLiw7isPVNlK-crsAOKkfOZe8SjZ69G4LbdmcEBwPXHJjjQ9j6Kxn-bZVe9tNCqbia0PcSrFAf0-uuXUt-5CMUp4ci_y3SNoMImnTDupy2tGoe-js_m3lyXzIM0sLQ9kxVDvt6eT8CyTOQL9ViKT-NMR8NMBAUPV21ZhNENQYUsJlHPJbDEhwV5lt9OX1liltu-n_tLvU_NFxsOIOjmpIVl2Uhsjhy0m00 "merged tags")

### Sample with tag dependent sprites and custom legend text

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

!define osaPuml https://raw.githubusercontent.com/Crashedmind/PlantUML-opensecurityarchitecture2-icons/master
!include osaPuml/Common.puml
!include osaPuml/User/all.puml

!include <office/Servers/database_server>
!include <office/Servers/file_server>
!include <office/Servers/application_server>
!include <office/Concepts/service_application>
!include <office/Concepts/firewall>

AddExternalPersonTag("anonymous_ext", $sprite="osa_user_black_hat", $legendText="anonymous user")
AddPersonTag("customer", $sprite="osa_user_large_group", $legendText="aggregated user")
AddPersonTag("admin", $sprite="osa_user_audit,color=red", $legendSprite="osa_user_audit,scale=0.25,color=red", $legendText="administration user")

AddContainerTag("webApp", $sprite="application_server", $legendText="web app container")
AddContainerTag("db", $sprite="database_server", $legendText="database container")
AddContainerTag("files", $sprite="file_server", $legendText="file server container")
AddContainerTag("conApp", $sprite="service_application", $legendText="console app container")

AddRelTag("firewall", $textColor="$ARROW_COLOR", $lineColor="$ARROW_COLOR", $sprite="firewall,scale=0.3,color=red", $legendText="firewall")

Person_Ext(anonymous_user, "Bob", $tags="anonymous_ext")
Person(aggregated_user, "Sam, Ivone", $tags="customer")
Person(administration_user, "Bernd", $tags="admin")

System_Boundary(c1, "techtribes.js"){
    Container(web_app, "Web Application", "Java, Spring MVC, Tomcat 7.x", $tags="webApp")
    ContainerDb(rel_db, "Relational Database", "MySQL 5.5.x", $tags="db")
    Container(filesystem, "File System", "FAT32", $tags="files")
    ContainerDb(nosql, "NoSQL Data Store", "MongoDB 2.2.x", $tags="db")
    Container(updater, "Updater", "Java 7 Console App", $tags="conApp")
}

Rel(anonymous_user, web_app, "Uses", "HTTPS", $tags="firewall")
Rel(aggregated_user, web_app, "Uses", "HTTPS", $tags="firewall")
Rel(administration_user, web_app, "Uses", "HTTPS", $tags="firewall")

Rel(web_app, rel_db, "Reads from and writes to", "SQL/JDBC, port 3306")
Rel(web_app, filesystem, "Reads from")
Rel(web_app, nosql, "Reads from", "MongoDB wire protocol, port 27017")

Rel_U(updater, rel_db, "Reads from and writes data to", "SQL/JDBC, port 3306")
Rel_U(updater, filesystem, "Writes to")
Rel_U(updater, nosql, "Reads from and writes to", "MongoDB wire protocol, port 27017")

Lay_R(rel_db, filesystem)

SHOW_LEGEND()
@enduml
```

![tags with sprites and custom legend](https://www.plantuml.com/plantuml/png/dLHTR-Cs47pth-0Pzs03ZfLpcWOewiCvTjhhmRca_cWUXHMvbjLIf4fISOoY__r8EX8TM_b0yXHnPsQ7kqD_qGQKANFU-f09oak6P6rCeN-98WMRVfgPTPcK6XMLmg0mVIhpgE0W7ET46yQp91h_T7BhZfRNqqWXHz2ee_l1-Qcjn6DBX4oWwXUkJUi3mvNz95B3hJruGxkn0hr6bcU2HLMV4rcWq4XBbPajABhE359JAXoSP9QhenoqGLNTgcuNZMMUI-6z71UNjdC4dE_AeVwhNAqoYj4SrJqg7J4ma836MFk3pyyZLnb_0mgAWcSKJ2R5ys0xI8g5qP53s8DuZ_KIV9Kft03ddrkj4MDN3mQL07vh-qgnWBJJ1Y75DfUbZl71j7laeoxiL77ObXfYjumuuK3_YTVWgnnJ56nXiSD09GxNxheEUygqr4Rcg1f5EQWKurJ9iZYIJLE5AHXapRhWmj0e2YNBJ8zABjLG8Gl2ysQafi1nUDeVd1-HWXlNBTD6-L5NZfobEjlUrGQJKL7isphUww6svH2B8hHIiif7mYpP5mtXQr0CvPSbNIxrlgexQ5Rq9R8hlIngYmS3Q8ZgeRebQSdnQ0fEVeRS2rSHTbnZMME_glR7qMnsSnUFRwOtCozhgKsbOAXMgXT_zjpU0zQPsOKljg-dKsVUvwX7sfSoySOWrSE3nzHz97P2eYlM7F8U-UDU2gp9uRq4tfFirHrH2HPe7kHSphVQO1vVob8mKDiE_MJ11kdQg2n1tVzRjxl_jOZzgnVNiGbqwx70Eqp8wCcYsj_W7dh4lHsHakk_nZsoaBajaul-Gzs_2dxtgV8awIZaCKkiZbsarmHE9e_vTFBNs_cVKtBUFzzNOycXKiUdrT_DadvpSTpTjEq-HukpGM1xQ8CL8VM_tCA_IzVIcI1p8zNEXXIfd5oIGN_mYf6oO63y2fQx_weXaGk7ya5semWRbM8tclzRBJk4e_24wIyrQgVsTR6udGU144BF3pbwdy11eDuXubLgmjw6WMcoKZ8d81ZPkEUcYP5Ep4uy-ZQvjEaff3BaxEpqvvsRe1Cs_4Jh45PjCI3szxUnBacXf95KyiTcWulJJnUFjkDbME0hnYqANdCVv0xytzMNFyA52pIFwytNcS8sdjKFBBItfVbN-yitlVhzwlkaqsrzGS7AdFy0 "tags with sprites and custom legend")

### Sample with different boundary tag combinations

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Component.puml

' Update the generic boundary style and the "system", "enterprise", "container" boundaries styles too
UpdateBoundaryStyle($bgColor="gold", $fontColor="brown", $borderColor="brown")
' (Re-)Updates the system boundary styles; re-set $bgColor avoids '(no back color)' in legend too
UpdateSystemBoundaryStyle($bgColor="gold", $fontColor="white", $borderColor="white")

Boundary(b, "A Boundary") {
}

Container_Boundary(cb, "A Container Boundary") {
}

System_Boundary(sb, "A System Boundary") {
}

' defines a new border style incl. new border type
AddBoundaryTag("repository", $bgColor="green", $fontColor="white", $borderColor="white", $shadowing="true", $shape = RoundedBoxShape(), $type="GitHub repository")

Boundary(c4Respository, "plantuml-stdlib/C4-PlantUML", $tags="repository") {
  Component(readMe, "README.md", "Markdown")
}

' boundary tags are internally extended with '_boundary' that it uses a different name space
' this enables different element and boundary styles for the same tag name
AddBoundaryTag("v1", $bgColor="lightgreen", $fontColor="green", $borderColor="green")
AddElementTag("v1", $bgColor="lightred", $fontColor="red", $borderColor="red")

Boundary(anotherBoundary, "Another Boundary", $type="BOUNDARY TYPE", $tags="v1") {
  Component(anotherComponent, "Another Component", $techn="COMPONENT TYPE", $tags="v1", $descr="Component and boundary use different tag name spaces that both v1 tags can use different styles")
}

Lay_R(b, cb)
Lay_R(cb, sb)

Lay_D(b, c4Respository)

Lay_R(c4Respository, anotherBoundary)

SHOW_LEGEND()
@enduml
```

![custom border tags](https://www.plantuml.com/plantuml/png/bLH1RzfC4BtxLyndHSAM0dofqaihf110oI5018cgdD3QEzYhc5rhTmr1LVzxTrXC7DDMoYdPDpDldkVDS6CiqxRQ5C5_GgP5nH5oQqlphT_NRDVBXCshf3AeKoKjIjjBrQPV5anIJTTONeYaFxhkFXBqF7teQooG6JJzxPUl_xl8QgGsfP9KMbARe0FF9MSMmUO86KhK8eL4LP8plGTZzmK2a_mG3itUMDo4bn0w0jIb5WRfHMgOSBLXNIhG-683Lgd0zxWzqYuf45qasKWLIW_2J1NSqLoi7SqHIhJQIS8IfJdg3sZiH4SBxCQUrHoqUMajvUOxQEmQj50t0xPLWXleH591mj9NI0cEEo0a59YXv0t1omFf9sJlSc6n9Rj6uo2ecQB43Mq8zJECuMVmAmX6zHXNfyJKPvuYPpLUudk1yGKUFilk0CUrup70GE8ElCoZpRHnlIPizoK6GyvhbYUMHQ76KXbXbIEzXCOmDAByn3GSQdB6rKx8R11QNTLGYJ201NL4r_XjIKWKknYf6OHtmjvN2JHKDEUQNY_Gr14tY7-SHaYKB3E3vXVHc01EDn9fP7oAZcWn6Owdazw630-dJBzoluaqq_Ub8pvWcaPfKKjM57l0DulqBR0JDeVEgaxkWCsP1M6XCWS_k5YlKQEq8Da6mPGinO2oX06KB2dGD7Amm0tzPPAtbnxMIlkRS3oaYGZFZTnUVJ2m45bk_-IYnzekUZGcrecNybTIZUqp8QHDI5ZJIYQLpL7NRzfgGfedS5gAs_dpR3nSlC3Jo-FaP2o9QHbQivw01kq9En1Wcij1E9fF7-UpoUpfZ9d-vsXIfzmNjiqWMnj-kRg6hyQRdxZEiBtoUvCosQhnTlejUs3xrO9-Dz8aFZvIzp99x6DZYdrO_xWkQXr5Qx0kRNa__x5wcDnDPkCe3cvGSdSolm40 "custom border tags")

### Custom schema definition

If the custom (color) schema is defined via `UpdateElementStyle()` then the legend of existing elements is updated too.

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Context.puml

!$COLOR_A_5 = "#7f3b08"
!$COLOR_A_4 = "#b35806"
!$COLOR_A_3 = "#e08214"
!$COLOR_A_2 = "#fdb863"
!$COLOR_A_1 = "#fee0b6"
!$COLOR_NEUTRAL = "#f7f7f7"
!$COLOR_B_1 = "#d8daeb"
!$COLOR_B_2 = "#b2abd2"
!$COLOR_B_3 = "#8073ac"
!$COLOR_B_4 = "#542788"
!$COLOR_B_5 = "#2d004b"
!$COLOR_REL_LINE = "#8073ac"
!$COLOR_REL_TEXT = "#8073ac"

UpdateElementStyle("person", $bgColor=$COLOR_A_5, $fontColor=$COLOR_NEUTRAL, $borderColor=$COLOR_A_1, $shadowing="true")
UpdateElementStyle("external_person", $bgColor=$COLOR_B_5, $fontColor=$COLOR_NEUTRAL, $borderColor=$COLOR_B_1)
UpdateElementStyle("system", $bgColor=$COLOR_A_4, $fontColor=$COLOR_NEUTRAL, $borderColor=$COLOR_A_2)
UpdateElementStyle("external_system", $bgColor=$COLOR_B_4, $fontColor=$COLOR_NEUTRAL, $borderColor=$COLOR_B_2)
UpdateRelStyle($lineColor=$COLOR_REL_LINE, $textColor=$COLOR_REL_TEXT)

Person(customer, "Personal Banking Customer")
System(banking_system, "Internet Banking System")

System_Ext(mail_system, "E-mail system")
System_Ext(mainframe, "Mainframe Banking System")

Rel(customer, banking_system, "Uses")
Rel_Back(customer, mail_system, "Sends e-mails to")
Rel_Neighbor(banking_system, mail_system, "Sends e-mails")
Rel(banking_system, mainframe, "Uses")

SHOW_LEGEND()
@enduml
```

![custom schema](https://www.plantuml.com/plantuml/png/dL9TRvim57tdLr3MXrHg0o6aGPCYjMHegqIJAX_Qtf2DRn9KOoBRhEs_dy5ik1dTfAWlpVcuznnVxeH4N5O5jIvobj6AW7sGyYW-kov7ByDzBWyLhWJmh6GIc1ncPU4UAMArvqP8GdFipeERfnhQFYOk1mf8W71_-XDFCUcyDhxAuR5UObrSpfV9SfNUfnDxPZkVfhinzaB7m8C6n-D9wDsQ-BZ1mGlzKM3YVeFl20vlnoO-qZY0XuqvYtYxMTqdcflMVnqNjHuI4WJOnFKEx2DCV1FNcK9lEaQPYUiEay2VXg69wyu-yRp0cB-AapHvMCGzmpIvYNzitf7MzaYGX9X20KokvHk5WNC4BahcNDkNU3ylQSbdtLihSAVkqC7TKzJwaXFW9vwH8iG1aV8bP_kP8ta5pbNlOdLTu0pHzCC4qHa9r3Nwruat8Q7exHcSqTF_JwaFrqLdh8kwTIkWUjKbpHaOgkw3K3Eaoc5mtVTmPLbFpNCFiah8iW1-RJiQGTIE47jMPxFdBQSkjsvw3B1csbhAyy3geY3_UBHGELfB6h_AGO5osddYc_gtBLhbYP3jE2f0oHv__zypMzKtal-LQYj0A9bIfH7AdWtf-oHhO4JOqEGHjYnRpmBo_K6z_qdTVxgrjS-XItIfhFMtvVSqYR_6Yo-3A-jEJQaA-Wi0 "custom schema")

## Element and Relationship properties

A model can be extended with (a table of) properties that concrete deployments or more detailed concepts can be documented:

- `SetPropertyHeader(col1Name, col2Name, ?col3Name, ?col4Name)`
  The properties table can have up to 4 columns. The default header uses the column names "Name", "Description".
- `WithoutPropertyHeader()`
  If no header is used, then the second column is bold.
- `AddProperty(col1, col2, ?col3, ?col4)`
  (All columns of) a property which will be added to the next element.

Following sample uses all 3 different property definitions (and the aligned deployment node).

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Deployment.puml

' default header Property, Value
AddProperty("Name", "Flash")
AddProperty("Organization", "Zootopia")
AddProperty("Tool", "Internet Explorer 7.0")
Person(personAlias, "Label", "Optional Description (with default property header)")

SetPropertyHeader("Property","Value", "Description")
AddProperty("Prop1", "Value1", "Details1")
AddProperty("Prop2", "Value2", "Details2")
Deployment_Node_L(nodeAlias, "Label", "Optional Type", "Optional Description (with custom property header)") {

  WithoutPropertyHeader()
  AddProperty("PropC1", "ValueC1")
  AddProperty("PropC2", "ValueC2")
  Container(containerAlias, "Label", "Technology", "Optional Description (without property header)")
}

System(systemAlias, "Label", "Optional Description (without properties)")

' starting with v.2.5.0 relationships support properties too
WithoutPropertyHeader()
AddProperty("PropC1", "ValueC1")
AddProperty("PropC2", "ValueC2")
Rel(personAlias, containerAlias, "Label", "Optional Technology", "Optional Description")
@enduml
```

![properties sample](https://www.plantuml.com/plantuml/png/XP9HRzCm483VyojCNfPANT95J4WyRUf089MjWW8IBvMR78qbnsVvpXi1yT-netNjkfGy-UpxxkBld2jYwTYtEdcbJALz3Q9XjlIsA9nyoBUA6x_n1Av2ms0uhx0jh9OcrfmJrrfjYldhysKy-lffKJZG80cek2ylPo6plW6hiMjZhOtVISv43J-bromQa3KuiNHemN4t5T-azf1Sr_NkA4jlPGlfLAJljQGcdJnFthcjDEgtP8KcGZyG6QsInzmAKSVyHyFW3B1uzyjgTE34ctmMu2KuGfFPVhdMIbA05t83VTMTZVsb5ZT0bLFzJcGFYfid4_lugKUbIUYPV07UtU13VvgbktqwJQDgBtRGzFZQCRg8J0-7AD8ibQQB8RHyGii3j0pe_WtMjrZ3Uf6Pi9mMNNKMHimhJupjWBZuaoH2V0yC-kC1J4BcnRNdUyKG3YDxjH16P8ucs1bmMRMBNkYie6eCQjns_tT1F_Y0VyCJTiJGPjGlG-CQxwY0OhFaJ13Bi3LR4GbndvVvPJuJ3hICXTGeIuAyjUWEYmKZ9gUcEJhBqKb-1ltyjpyUvu3k-5n3uoimjM_rFm00 "properties sample")

## Version information

C4-PlantUML offers version information like PlantUML with its `%version()` call.

- `C4Version()`: Current C4-PlantUML version (e.g. `2.4.0beta1`).
- `C4VersionDetails()`: (Floating) version details with the current PlantUML and C4-PlantUML version. (It can be referenced via the alias `C4VersionDetailsArea`.)

```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

' existing plantuml version as text
%version()

' new C4-Plantuml version as text 
C4Version()

' new C4-Plantuml version details (incl. PlantUML version) as table
C4VersionDetails()

' version functions used in e.g. footer
footer drawn with PlantUML v. %version() and C4-PlantUML v. C4Version()
@enduml
```

![version sample](https://www.plantuml.com/plantuml/png/ZL2zJiCm4Dxz5CU0Q8VQ29M5gL8OGMA15JdnDRNadYFVkUdZOnEiTc3ebEY-V-zOR99y3EhEqn2oGpY8JFnYJBAp7hqSSfyPqn19a4GFyMYcOAbgDYmk-Dvqsyr7FNs-lvc40IqZczFJysD1lhiYj9umwQd6g0V0isVnD4BpWHCczf70CWYUHTt_7LRhoYUSeKNymmRLRRzkuJiiHGB3gYxLq2etVFrhQFk05yFNHRBuDfzzfa7A3qDcTE09K8yQzZ4A9hLym2Kx4ypb_Qw2D5oMWINNQZRqUiWEoPNsFm00 "version sample")

## Snippets for Visual Studio Code

Because the PlantUML support inside of Visual Studio Code is excellent with the [PlantUML extension](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml), you can also find VS Code snippets for C4-PlantUML at [.vscode/C4.code-snippets](.vscode/C4.code-snippets).

Project level snippets are now supported in [VSCode 1.28](https://code.visualstudio.com/updates/v1_28#_project-level-snippets).
Just include the `C4.code-snippets` file in the `.vscode` folder of your project.

It is possible to save them directly inside VS Code: [Creating your own snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets#_creating-your-own-snippets).

![C4-PlantUML Snippets Video](images/vscode_c4plantuml_snippets.gif)

## Live Templates for IntelliJ

### Prerequisites

[Graphviz download](https://graphviz.gitlab.io/download/)  
[PlantUML Integration](https://plugins.jetbrains.com/plugin/7017-plantuml-integration)

### Install

1. Download [IntelliJ live template](intellij/c4_live_template.zip).  
2. Select `File | Manage IDE Settings | Import Settings` from the IntelliJ IDEA menu.
3. Specify the path to the downloaded ZIP file: `c4_live_template.zip`.
4. In the Import Settings dialog, select the Live templates checkbox and click OK.
5. Restart IntelliJ.

### Usage

- Create new PlantUML file (.puml).
- Type `c4_` for displaying artifacts templates for C4-PlantUML
- Live template create correct C4 model artifact with stubbed arguments.
  - E.g. alias, label, type, technology, description
- Replace stubbed arguments with desired values.

![C4-PlantUML Snippets Video](images/intellij_c4plantum_live_template1.gif)
![C4-PlantUML Snippets Video](images/intellij_c4plantum_live_template2.gif)

## Advanced Samples

The following advanced samples are reproductions with C4-PlantUML from official [C4 model samples](https://c4model.com/#examples) created by [Simon Brown](https://simonbrown.je/).

The core diagram samples from [c4model.com](https://c4model.com/#coreDiagrams) are available [here](samples/C4CoreDiagrams.md).

### techtribes.js

Source: [C4_Container Diagram Sample - techtribesjs.puml](samples/C4_Container%20Diagram%20Sample%20-%20techtribesjs.puml)

![techtribesjs](https://www.plantuml.com/plantuml/png/ZLHTS-es47tthzZoSc662xcaQMRwT4b8atjBFXgRPlhaaQt5A9KbLv93c4x_UrUoO-BG6Se3DgkpgtDsp_BLEcPSNShe1w5oMNE4ZNEL_NawDMmxAOJRr5bjqUHQELHkakjoMaccVCvdwxWKsVJonyyFFhIwNKuDIcGMxVHbTdP29-ab9JAXq4mgVyqdg1NLAAaMk0t2Makfjq8L80a4J77e7GjZwKq3SG2fSoRbZcfqP0ylY9RpF-vNIPhSFwIB-wUxuIZwr8RcSHh_UfLStb2i3JrzIsxIvTNrrTs2Wb7qWCPgbLwzkY5JMkrANTlKwn_3OFuMW1K51gCMF6H5OR1W3dc7x28VeRmKIbXdc1DQTV1Uz2qbYdVMOPbUw5fnPdR3_0jX7UORPqI6Tl9i1wE_8w1F-EhwCDnYbhAg8lGJPZ2lAYdoK7f0eU_iXOqXhepl-UtlbsD8T4d7S3vvzUTpFmyBdfhrZNyHk8KATILn3CtDOsZTC0PyeGS5ddL6t-Zo2QoDBcbsxRZ04nu35sGb9iDyloLWCNVQY-mpNsH3WpBb6V5uH1auKzA2EPOnYvxUxIx-RGbdaxE6RKnbq1xm2qyeiSn8nKPK567oJ_kHRyPuuU7NmjtK6HYiTAlYWDfmBIJQC16wzXVw0Sry1lxdF3cTlQDZaPby0q9nV4NxNpALjdz9IhZJ92S8X90R96fLwCK5p2QpdiZGsCSudiuTlQmHkOLX9dK1HDlPKMYkso8wUqY_hZXpmMshvktD2t3kKLPBz4uPT00BbT51zBWjskzJkAtr0MW536o-GLvBv4334fx3Fvs9_KAvhN0DXQHv8yIxu-Q_XawRM_g7NgQbimjw1dKH-UDWHVV6fnsoNijDaZp4X2TqVq-Fm_kxUZGbv7J7xspCU3iwtx2j4RwrJljK6ltq--A2Lh3Ini7fwSbFLAXNf-UwVQsFi62d7kAzaRR2e9-cqxcMxMMpyvClvotjTDNPunXnGh4Zx7lbUloVEl47k23WIBl-hvnzrRtZhj5rXWQXrjgKOQpxdUdQrasqLshlJeBsAsIwTb3LcHGvv9fZin_2QIFmIDNMrg5ejqor5QhmYnx8TSlUB-MrBjakVUp-CVUj7aLVKV6wbFy2 "techtribesjs")

### Message Bus and Microservices

Source: [C4_Container Diagram Sample - message bus.puml](samples/C4_Container%20Diagram%20Sample%20-%20message%20bus.puml)

![messagebus](https://www.plantuml.com/plantuml/png/ZLNVZnet47xdhvZIIkKaSZHH-rBffF03DOcuEyA2yeXcTuTTArvxPNkvqAh_UyUxu9ZSddeyW3qUVzytyzdclNLeN5F9mKz2PRB92KhdQlldP6BmwROGhcpInfB9j7Aat6scgqajKVazRwpBfKWdyz_Vh7reTx-Q69A4bkpa-EwFttXbF-UDA1IPszhJ_0gDOeoAiS2L10SjfNuIgW39IO0gXwjbOIoFDB06a3f3AK-C4SG-9nXCytmfoIDiiHWDAv4PdP0vYeo6O_Z5bbZJtL8KfKj4JddYvwCRNacBkPRQt0tdsgW3go8paqsxwS0SvyMdKhWs9gaWbM_fcxlhIC1sB30YZmxMmzyCRtvKP9qsM4HYDhfHd3hJtth4o5RfrzDBKXX_a7nu_B9VBpV9uyF-SRTTVNnOZZYy9cEr6cKDCrPanZ0Fe-4KBk4Mu6GTLVkP5uBcDChUSieb6pwgWpOLEg7Ly0R-6G1_GjT7MDTnyhIkfSYwP8v_mYFQp8ZQZM6gYaQYyU6fTzq63TPRNA72Whpjma1jz458hkwQBHIpFpSxfWukTxHZI6hZJzPCQ-U3svAWra8vq0V0B2DhWIiBAa14XNAh7HOMxY0-Giy5LOp2ilTfOvdYlfl1hB6USODfAjpzvvRTeBArDgxbv7IXl00wadBs6QmXdyhgeq8tbrXSwQP9J_vtRWWTML2-0YaivP2ZmvOiW47Tc5fRigyk3vjSk4Z3rCzZ_ldFazk7vTOFrqOVHSuQj2bG2TisyiqJXw25yG8Ec0d9mzTBMAJVJS_JsEy5EapHjZ8U3MQIuEsxpCyIfmtP_pMskubzZA5ZdZBkVCnvVqe-ho8wl3J_RyhXICOoNNlKfFpkTp05SoXrrkjDZy9-MtWrCiNFl9pbaLIO1dLH3m1JtRZpqGDNeeCIZyHVTKsAydu5_mu66vBxHVIWT7T_ruaUVjXkrmaddjFQnPxxkgjpT2-u0xvDXGT3UrBP63xncpQv0jxrl06TZeHKRaDLsgDyeJJHsLTolFkbpT4D3Y11MzEAZK1Rd1wK-8o6dhTcY-uXNCpcvnAktuoUc_vA4LSmuQA-6gB5w64FeTvIEkeVsEBZ67PqNDsUmGfF-qqVsnNIvRzijVnh-R0OtGpUSnLD9Vy3 "messagebus")

## Background

[PlantUML](https://plantuml.com/) is an open source project that allows you to create UML diagrams.
Diagrams are defined using a simple and intuitive language.
Images can be generated in PNG, in SVG or in LaTeX format.

PlantUML was created to allow the drawing of UML diagrams, using a simple and human readable text description.
Because it does not prevent you from drawing inconsistent diagrams, it is a drawing tool and not a modeling tool.
It is the most used text-based diagram drawing tool with [extensive support into wikis and forums, text editors and IDEs, use by different programming languages and documentation generators](https://plantuml.com/running).

The [C4 model](https://c4model.com/) for software architecture is an "abstraction-first" approach to diagramming, based upon abstractions that reflect how software architects and developers think about and build software.
The small set of abstractions and diagram types makes the C4 model easy to learn and use.
C4 stands for context, containers, components, and code — a set of hierarchical diagrams that you can use to describe your software architecture at different zoom levels, each useful for different audiences.

The C4 model was created as a way to help software development teams describe and communicate software architecture, both during up-front design sessions and when retrospectively documenting an existing codebase.

More information can be found here:

- [The C4 model for software architecture](https://c4model.com/)
- [REAL WORLD PlantUML - Sample Gallery](https://real-world-plantuml.com/)
- [Visualising and documenting software architecture cheat sheets](https://www.codingthearchitecture.com/2017/04/27/visualising_and_documenting_software_architecture_cheat_sheets.html)
- [PlantUML and Structurizr - Create models not diagrams](https://www.codingthearchitecture.com/2016/12/08/plantuml_and_structurizr.html)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
