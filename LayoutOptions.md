# Layout Options

C4-PlantUML comes with some layout options.

- [📄 C4-PlantUML](README.md#c4-plantuml)
- [📄 Layout Options](#layout-options)
  - [Layout Guidance and Practices](#layout-guidance-and-practices)
    - [Overall Guidance](#overall-guidance)
    - [Layout Practices](#layout-practices)
  - [LAYOUT_TOP_DOWN() or LAYOUT_LEFT_RIGHT() or LAYOUT_LANDSCAPE()](#layout_top_down-or-layout_left_right-or-layout_landscape)
  - [LAYOUT_WITH_LEGEND() or SHOW_LEGEND(?hideStereotype, ?details)](#layout_with_legend-or-show_legendhidestereotype-details)
  - [SHOW_FLOATING_LEGEND(?alias, ?hideStereotype, ?details) and LEGEND()](#show_floating_legendalias-hidestereotype-details-and-legend)
  - [LAYOUT_AS_SKETCH() and SET_SKETCH_STYLE(?bgColor, ?fontColor, ?warningColor, ?fontName, ?footerWarning, ?footerText)](#layout_as_sketch-and-set_sketch_stylebgcolor-fontcolor-warningcolor-fontname-footerwarning-footertext)
  - [HIDE_STEREOTYPE()](#hide_stereotype)
  - [HIDE_PERSON_SPRITE(), SHOW_PERSON_SPRITE(?sprite), SHOW_PERSON_PORTRAIT() and SHOW_PERSON_OUTLINE()](#hide_person_sprite-show_person_spritesprite-show_person_portrait-and-show_person_outline)
    - [Using HIDE_PERSON_SPRITE()](#using-hide_person_sprite)
    - [Using SHOW_PERSON_SPRITE()](#using-show_person_sprite)
    - [Using SHOW_PERSON_SPRITE(sprite)](#using-show_person_spritesprite)
    - [Using SHOW_PERSON_PORTRAIT()](#using-show_person_portrait)
    - [Using SHOW_PERSON_OUTLINE()](#using-show_person_outline)
- samples
  - [📄 Core Diagrams](samples/C4CoreDiagrams.md#c4-model-diagrams)

## Layout Guidance and Practices

PlantUML uses [Graphviz](https://www.graphviz.org/) for its graph visualization. Thus the rendering itself is done automatically for you - that it one of the biggest advantages of using PlantUML.

...and also sometimes one of the biggest disadvantages, if the rendering is not what the user intended.

### Overall Guidance

1. Be minimal in the use of all directed relations - introduce the fewest possible directed `Rel_` and `Lay_` statements that achieve the desired layout. One way to do this is to immediately remove any of these you experiment with when they don't actually affect the layout at all. And of course you will remove the ones that affect it the layout in a negative way.
2. With dynamic rendering tools (e.g. VS Code plugin) do NOT trust the first rendering as it is shifty when adding code because you do not know exactly when it grabs the current unsaved code. Wait for a bit or close and reopen preview panel.

### Layout Practices

These are intended to correlate to the layout engine’s algorithm, but have (as of this writing) been determined by trial and error - not a code review.

Please read through all practices before starting.

1. Create all components, containers and boundaries first - in order top to bottom or left to right.
2. Use `Rel` (directionless) to create initial relationships.
3. If layout is not as desired, modify **some** Rel statements to contain direction `Rel_{direction}` to force shape layouts.
4. If the layout is not as desired, sparingly add `Lay_{direction}` to force any layouts that `Rel_{direction}` does not correct.
5. For both `Lay_{direction}` and `Rel_{direction}` statements used above:
   1. Exhaust attempts to get a working layout with `Rel_{direction}` before adding `Lay_{direction}`
   2. Try to introduce the fewest possible directed statements (of either type) that result in the desired layout.
   3. Immediately back out any directed statements that do not change the layout at all.
   4. Order inner objects first when it creates the desired result (enclosing objects tend to follow suit when child objects are ordered).
   5. When ordering multiple objects, only specify one relationship and, if possible in the same direction. For example if you want entity1 => entity2 => entity3, then `Rel_R(entity1,entity2)` and `Rel_R(entity2, entity3)` is the minimum possible statements and they all specify the same direction.
   6. Try NOT to apply directed statements to both inner elements and enclosing elements to force relationships that aren't working out.
   7. Make all orderings at the same nesting level whenever possible.
   8. Do NOT create duplicated, opposite direction statements in an attempt to force or ensure relationships as it does not affect the results. For instance if you have `Lay_R(entity1,entity2)` which is not working as desired and then also add the opposing one as `Lay_L(entity2,entity1)` - it does not help with forcing layouts to be as you want them. It might help to use `Lay_L` **instead of** `Lay_R`, but not both together.
6. Do not create an "All enclosing" boundary - the code for processing relationships seems to struggle with relationships inside this. Additionally, `SHOW_FLOATING_LEGEND()` will not display inside the All enclosing boundary.
7. Legend statements must come after at least one usage of each of the elements you want the legend to contain.

## LAYOUT_TOP_DOWN() or LAYOUT_LEFT_RIGHT() or LAYOUT_LANDSCAPE()

With the two macros `LAYOUT_TOP_DOWN()` and `LAYOUT_LEFT_RIGHT()` it is possible to easily change the flow visualization of the diagram. `LAYOUT_TOP_DOWN()` is the default.

```plantuml
@startuml LAYOUT_TOP_DOWN Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

/' Not needed because this is the default '/
LAYOUT_TOP_DOWN()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_TOP_DOWN Sample](https://www.plantuml.com/plantuml/png/JL1DRzD04BtxLmpX44TAlRI22wUQWE3G9XPng3XPQ--KhBGVgvqnLeNuxyoAqk3Ba-TzpDkv9TQPP--gLpPCRZO8P-P4xvNAUcb-M3xFuqoOfnWO0pTJz2ev7OhdYjWuEwhTswkkZ4xtTogZGqr8wkVDkpV233inQXimDwcigTGQzf4X81eqCEAa9HxuR0ai2I8OVDIpOrYhwgxzVZZrGt_eXe-7XtszgQeECyLGQ-DjsCAgBMY9i-QOLvlg-4ICVlWGvs1qVggdwosiZzedX-iD_Af0lfTAzOBZe5EId0SSeKt9sKcpZM4bezthBRJ7hjb_wiMI4MwQQxZ_jYjSwrnS2Cfb23Y2d2LfaNWfRcKNz8jbnWniFJhPHTBjztExcl-IalCi4xBwYkxVgowrJYHEmIzztnr5LKGlx2NcCpB9BnPupD7_Rxd5OEJoVm00 "LAYOUT_TOP_DOWN Sample")

`LAYOUT_LEFT_RIGHT()` rotates the flow visualization to *from Left to Right* and directed relations like `Rel_Left()`, `Rel_Right()`, `Rel_Up()` and `Rel_Down()` are rotated too.

```plantuml
@startuml LAYOUT_LEFT_RIGHT Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

LAYOUT_LEFT_RIGHT()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_LEFT_RIGHT Sample](https://www.plantuml.com/plantuml/png/JKzDR-8m4BtdLtZP0q62P46xbpsHHXGgGHkHqAgdo4ccnP8_B7lI25Nzxnsh5EhBoFFUc_VUqYDts2iP_HAwbNq7x8Xe_VyqTNn8NWKU-wRtu5gZ4JGchL6fbLm7pSnZ9qMJvdzdHLWTTjlKWGJkmQTlYtz_2Abp4dAXmIKss4JRxFdXKDNRrMrLx-_McogUH541pXiTyqu9FMMZB4pXqN4qRZI9ofD7KFMDwNN7tIbkvrCsBhco4iOJzXunUXUVU82cvjRIdITeM6Qj52r7OVI8LldlASlA8hbVLIHnm1R9dEqUyu1bKfh1ir3NCpICkbfE5DLB5EJ5ga4WWcCe54ZoyfJjuvmknY-Gxfnf14PxaD-jhh4EdfGqDrLLbCGAf0jwFRC6zFI5C5wSKJybIz1Th-Gd "LAYOUT_LEFT_RIGHT Sample")

`LAYOUT_LANDSCAPE()` rotates the default flow visualization to *from Left to Right* like `LAYOUT_LEFT_RIGHT()` additional **directed relations** like Rel_Left(), Rel_Right(), Rel_Up() and Rel_Down() **are not rotated** anymore.

```plantuml
@startuml LAYOUT_LANDSCAPE Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

LAYOUT_LANDSCAPE()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")

System(S,"S")
System(SU,"S Up")
System(SD,"S Down")
System(SL,"S Left")
System(SR,"S Right")

Rel_Up(S, SU, "Up")
Rel_Down(S, SD, "Down")
Rel_Left(S, SL, "Left")
Rel_Right(S, SR, "Right")

SHOW_LEGEND()

@enduml
```

![LAYOUT_LANDSCAPE Sample](https://www.plantuml.com/plantuml/png/JOz1Rvmm48Nl_0ftUmWhRQ29sajFeR1A3cI35cZK4_B296l9s9Oz54LL_tjc4h9PNwptlPatCpS1fSTfrD4NPNez3I2EY2xyJ5Clv-HPuN4wJ05yRms2mQItO-gqDDnp6N3Gwf3ctoyhHkrzcNhG80E4zE_rZs_aT3arIcN09ux7H6Nsvw5jkZBR5NMULTju7KKL-61DB8THcOrOPVohW5wYzQjrLBy4XB7xPISpIFyIzrSRSL7BqMcuM8j_aQ1t6XFFSEYaSvJp20UHEQTLBr5PioAKVzs8hAwItRQX5W_YEhaIzxzpzZAjxHm4Nni4Ma6dEaabuwHHqIpHp0eHl40rWgPPWNRxlsmNuxj9EKiPcT4UzCTLdskrWJhflskQggOgBZgvdp6tW84ayFVaxNZUyZ6qtgn8dbHBKhJkZ1HC2ZkRCrOoA-49pzYUsLuz7t5PksiTfOkwvOKvaHa7lT62A8k5SzWRBucpM3W7lXjxCaxnzTt3OrTkRxUx8bv7Ds26QTIl "LAYOUT_LANDSCAPE Sample")

## LAYOUT_WITH_LEGEND() or SHOW_LEGEND(?hideStereotype, ?details)

Colors can help to add additional information or simply to make the diagram more aesthetically pleasing.
It can also help to save some space.

All of that is the reason, C4-PlantUML uses colors and prefer also to enable a layout without `<<stereotypes>>` and with a legend.
This can be enabled with `LAYOUT_WITH_LEGEND()`.

```plantuml
@startuml LAYOUT_WITH_LEGEND Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

LAYOUT_WITH_LEGEND()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_WITH_LEGEND Sample](https://www.plantuml.com/plantuml/png/JL1TJy8m57tVhwZum4XW4w8lFZ4d0HF0nGs9JqktNQL9FvhsreKO_xjjH70lDxlduvpRkKLgq0aUNJ7PSjS1EI1gUv-cXlR91yE3Qvm5qog9835fbKWrfp9e9XOxpfeqlvqKORNRh5C37AW5ctxExcuyKkTA8cKIJA93JBJEtfvtLRr_gbRrUh5SR1_ZKHGLOAoICUq4asCooC9a5Wr5PGQZg3nQ154_A2SxQevnEnsJOKc5vZ0SaQ-8-EyS5FVGr5HhxxE7XcHQSzPIP4eE_2g_7fEiB9Bjel8I0sIMJCdcDGzOnhdgBGdtMeAAj4fewYd2SMIQ0wbwXWY681F0VPRrtRvFxMBy1RtFYUR1w0NutrMNMZl_G25lLLL5wLc1T4OlDaj0wtyXZ7UZn7_976Jd1Fy1 "LAYOUT_WITH_LEGEND Sample")

Instead of a static legend (activated with `LAYOUT_WITH_LEGEND()`) a calculated legend can be activated with `SHOW_LEGEND(?hideStereotype, ?details)`.

The calculated legend has following differences:

- only relevant elements are listed
- custom tags/styles are supported
- stereotypes can remain visible (with `SHOW_LEGEND(false)`)
- details can be displayed in different sizes via the `$details` argument
  - `$details = Small()` .. default; details are displayed with a smaller size compared to the legend labels
  - `$details = Normal()` .. details and labels are displayed with same size
  - `$details = None()` .. only the labels are displayed
  - if `$legendText` contains `\n` then the text before is the label and the text behind the details
- **`SHOW_LEGEND()` has to be last call in the diagram**

```plantuml
@startuml SHOW_LEGEND Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")

SHOW_LEGEND()
@enduml
```

![SHOW_LEGEND Sample](https://www.plantuml.com/plantuml/png/JKzDR-8m4BtdLtZP0q62P47RIq-aAO83qAW9vHWvoRHOyeTbJngXgl-zOvL2VHbvtiUyj_J87VPAHd-4RcNV0JiXMd-VfeuFoPl0Kz_q7bnhD8B6f3KgjPBhe9bvxAHeqlp_h0YhmswREf30FVZqVN7tZv0w9o4N6bnYmvce0EUDZdcdX9woKHQcyEWu6ZUQHENP8wZwmVIwu-uSj_Cf6vTSMGdZ2Vk86BshPJn0KtDhoUS83SkibQBbA8mUqIh_EsLPMIJxLKKI1soHpDdk9GzO9gKPF0lDF4F3g9RbH56zH46tM3K8H70CXG99jpnb-xoaY_4R99yBZS3e6UHFgrkiWoSbpKrL5IMn0kcAtcpMW9w-4CQhC-gt92etJyTwkrglze_n95g2xdeblm00 "SHOW_LEGEND Sample")

Legend labels and details can be defined via `\n` in `$legendTest` arguments too.

```plantuml
@startuml
' convert it with additional command line argument -DRELATIVE_INCLUDE="./.." to use locally
!if %variable_exists("RELATIVE_INCLUDE")
  !include %get_variable_value("RELATIVE_INCLUDE")/C4_Container.puml
!else
  !include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml
!endif
' $legendText with \n defines the label and details of the legend entry ("backend container" is label, "eight sided shape" is details) 
AddElementTag("backendContainer", $fontColor=$ELEMENT_FONT_COLOR, $bgColor="#335DA5", $shape=EightSidedShape(), $legendText="backend container\neight sided shape")
' $legendText without \n defines only a label 
AddRelTag("async", $textColor=$ARROW_COLOR, $lineColor=$ARROW_COLOR, $lineStyle=DashedLine(), $legendText="async call")
' if no $legendText defined, $tag is automatically the label and all additional displayed properties are the details
AddRelTag("sync/async", $textColor=$ARROW_COLOR, $lineColor=$ARROW_COLOR, $lineStyle=DottedLine())

System_Boundary(c1, "Internet Banking") {
    Container(mobile_app, "Mobile App", "C#, Xamarin", "Provides a limited subset of the Internet banking functionality to customers via their mobile device")
    Container(backend_api, "API Application", "Java, Docker Container", "Provides Internet banking functionality via API", $tags="backendContainer")
}
System_Ext(banking_system, "Mainframe Banking System", "Stores all of the core banking information about customers, accounts, transactions, etc.")

Rel(mobile_app, backend_api, "Uses", "async, JSON/HTTPS", $tags="async")
Rel_Neighbor(backend_api, banking_system, "Uses", "sync/async, XML/HTTPS", $tags="sync/async")

SHOW_LEGEND()
@enduml
```

![SHOW_LEGEND Sample, $legendText defines legend details](https://www.plantuml.com/plantuml/png/hLF1RkCs4BtxAsQrMTG67AljDfS21jPhgzqi73kmdRQ71OIHE9Q9fKY1fBmnYlvxXrAaEawANkg3eI4vZ--zUVpWF5fVbshm7UH67ybwa1w-INy0549wQJGgtYfBr0AKr0HeYxeaxU5wiKcMiztjRqbwkvel7nR9D9h4aqa4ta3j29J9KQdJu8tSmxiZMecPefGUfVDk65qsHwC1m1kfSrKBWdS5-RJlEQAgwRMMUFvJEZVQ8pEpaoeeUKFAqJdKmVlA_Hp75hzD2bPMPqpEvjp5AYQiBQuKwk32jVD2oOn1h-_3qiFTChQa21sv-FZZpVUlNgU5tBD_LueA_jxHuvE1NpG8slD91_v0e30Z1S56GGoW79Xzkz7q0PEn9nX66UPVGvrtzqGWNTizXeXaSV3Wf201xe0LXTqESGI3cH29eZ2V7HOzMCyv6iFLdekvKSPEhv9bSfUiTkalQ_wRhvVh3UzdHRiRlNt__cOnkmazpLNJ95o-3NTlGpqSZSzLJrzI_w9VyXszufMf_RbTHgiJOAkvaRGXrSX1Tz9vuEFfiTCmsspMl_VaGqJ_TMFhJugc2tG74akkBmMq-11Isz3at6hpZ6pBK0G6M0JdiVQcH2-Rf5_CcPVENv6Ghb9u8W6LDHLPBudxBOMkReBdOWEN-FzHRBpl58y6W-t9UIhJZwRM0krfcF_0mRhLdgmc3nzHVvMwY4Rmvm3ursTdM9fCAagnglZyNLF0hAeYhkPln_07bcYb3kMzDKSfWZnGifG-3B_E7Faky_rjMNiRx6kTjpv9ppuQo6l7pf9rS9GOUgI5bW08EigSWtH1xobzp4yoXTdzRI2dP8u1Dx3wZ4SSmyBmCVjFtpdV_-8Lg31mrCxVJL-yBoRrL-TlykY7Jp2fQvQ2RNniRx6apcTeJmSMMsziy4ofpgQS5tegt6XisQW1pCAJwJqQ0-OvZzFpbxUe7JQakIAVJvZKW4FrR7xFpNfmv9X1c_ynVDwkL_6dtUv-sojjjnY9WT9LUDMPkR3yGckFUXPa3idTyXBvBESXd9yumilarsIr68u67nYzBjNV "SHOW_LEGEND Sample, $legendText defines legend details")

Legend details can be deactivated via `SHOW_LEGEND($details=None())`

```plantuml
@startuml
' convert it with additional command line argument -DRELATIVE_INCLUDE="./.." to use locally
!if %variable_exists("RELATIVE_INCLUDE")
  !include %get_variable_value("RELATIVE_INCLUDE")/C4_Container.puml
!else
  !include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml
!endif
' $legendText with \n defines the label and details of the legend entry ("backend container" is label, "eight sided shape" is details) 
AddElementTag("backendContainer", $fontColor=$ELEMENT_FONT_COLOR, $bgColor="#335DA5", $shape=EightSidedShape(), $legendText="backend container\neight sided shape")
' $legendText without \n defines only a label 
AddRelTag("async", $textColor=$ARROW_COLOR, $lineColor=$ARROW_COLOR, $lineStyle=DashedLine(), $legendText="async call")
' if no $legendText defined, $tag is automatically the label and all additional displayed properties are the details
AddRelTag("sync/async", $textColor=$ARROW_COLOR, $lineColor=$ARROW_COLOR, $lineStyle=DottedLine())

System_Boundary(c1, "Internet Banking") {
    Container(mobile_app, "Mobile App", "C#, Xamarin", "Provides a limited subset of the Internet banking functionality to customers via their mobile device")
    Container(backend_api, "API Application", "Java, Docker Container", "Provides Internet banking functionality via API", $tags="backendContainer")
}
System_Ext(banking_system, "Mainframe Banking System", "Stores all of the core banking information about customers, accounts, transactions, etc.")

Rel(mobile_app, backend_api, "Uses", "async, JSON/HTTPS", $tags="async")
Rel_Neighbor(backend_api, banking_system, "Uses", "sync/async, XML/HTTPS", $tags="sync/async")

SHOW_LEGEND($details=None())
@enduml
```

![SHOW_LEGEND Sample, hide details with $details=None()](https://www.plantuml.com/plantuml/png/hLDHZzf647xdLymv5nKa3jgczr89AGJSvY8EJi2rVOY4nlO0gwnthTqnELJrltVM1jU1g_fI7f1dTsVc-xxvvhrdT5pcklCTfDOSo34eXg-Azu1PfbXPWrgkyXnD1beP0dIxCYV3S3TTnhFn-k6tUFCmdyoUf_4e6Wm7WmZOGka9j4rHwsFdHctXxG6TmaJJXbwKPz-DBfEZNWVWHfbKbnd1sntnfiave2xfjPJXvAVDn1f6GUO6HM1oGzfJkzIUkV0_3uSElmvsmgnC19nB9KjO38JRiD1eWWftdZEj4YbwznIEdXzdGqUQq9CV7dwy__xLTYPJMz7lLjDEljVqSXBmiu6CjlBI0-y9D2Qa8SYOaHJG7koslgZoGC2u8tIZ1DCl8KxFVI9GlixkGqHgjsVmAgCC_1uB2hVdYZteZBCirXJciyPTKwp17FNXTYl1n6hhHhVnB7wCv-lDBmlvconcYwNS9xlwDdhpxjtzT7mVSgfMepWqNuNUgn1tU_qswz4rzC_c6c_l5QrioMsvhD57m9DYWTAIT4K7_T6a0GzBved3UBbS_Dw03nRzruiL7pMDfkZtbCsKkIPGrOVWsWgc-DROzeiJmYmWm5rG7aksERAgd7unPpbgRr6cl1ZjA48KpXRaM97aEmfPvmcsoGOim_-7iMK-C-vrEgkZPyet7snfCdJ7Rlg36El1C3b331_GV55c5_NWpmx8h_5EDxU9acN4ef3tZrK0uwA899gywSCVcADJ9eHFpXvK5kY1LhdYCFmoySHdppVTaheRR4kJrZef5XqjfAKNPSbvE2WCESf13K2qEgXKZ7G1x-G-mQS4mlZf8O3JAiLGDw3wX0VimzJAC_TFNXllV-4AKAHmLC_VZwxsIq3zTTOtVk7kgSp6LqT1DdcsTPZJMMUeNmSKAxOkQARrMQPK3XeeacXTNh41JCBAD1hr0TDKnidonGwDnmgqHCJfG41rn5JVpEzRiPuzUK5G-xyFdrQB-V3ZUlsqQfYULgyN2ctcOQiJUo7v5TTJrPQHnIIFiulARPy7StuK2y_YN-Fvj7jxsehHtDRMVI_Dobp_3G00 "SHOW_LEGEND Sample, hide details with $details=None()")

## SHOW_FLOATING_LEGEND(?alias, ?hideStereotype, ?details) and LEGEND()

`LAYOUT_WITH_LEGEND()` and SHOW_LEGEND(?hideStereotype)` adds the legend at the bottom right of the picture like below and additional whitespace is created.

```plantuml
@startuml Layout With Whitespace Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

Person(a, "Person A")
Container(b, "Container B", "techn")
System(c, "System C")
Container(d, "Container D", "techn")
Container_Ext(e, "Ext. Container E", "techn")

Rel_R(a, b, "calls")
Rel_D(b, c, "uses")
Rel_D(c, d, "uses")
Rel_R(d, e, "updates")

SHOW_LEGEND()
@enduml
```

![Layout With Whitespace Sample](https://www.plantuml.com/plantuml/png/LT3FJeD040Rm-px5occRMDOOlNYg0j53rQQDyKYMtOcGB0lP6Vppziws2IqdPdxpVO6mGJAHfjwBgovOFpcGBT683rf7yvD_TTHEpOGGxH080kLswFNeJKYTDPBpNQEBk_KkqSVhLaVmO11GVz_Ut_2bBhXekW0n7zDhn0uY3a6PQvcTHlcOhSISKWqVvaq-PRmIs3PmwF271BsoJATH5ekgMrJBo-hCTVLB2lZ2proUqzLbMkp1r_lqZGshDTuZQy9IiLZ62U5i36vXN6Q0PACpT6HnU7d_hBVLS_LMgfNOG73yG_u1 "Layout With Whitespace Sample")

Therefore a floating legend can be added via SHOW_FLOATING_LEGEND(), positioned with Lay_Distance() and existing whitespace is reused like below.

- `SHOW_FLOATING_LEGEND(?alias, ?hideStereotype): shows the legend in the drawing area
- `LEGEND()`: is the default alias of the created floating legend and can be used in Lay_Distance() call

```plantuml
@startuml Compact Legend Layout Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

Person(a, "Person A")
Container(b, "Container B", "techn")
System(c, "System C")
Container(d, "Container D", "techn")
Container_Ext(e, "Ext. Container E", "techn")

Rel_R(a, b, "calls")
Rel_D(b, c, "uses")
Rel_D(c, d, "uses")
Rel_R(d, e, "updates")

SHOW_FLOATING_LEGEND()
Lay_Distance(LEGEND(), e, 1)
@enduml
```

![Compact Legend Layout Sample](https://www.plantuml.com/plantuml/png/LOv1Jy8m5CVl_HILKqbaLQCNJo2RQ3A1WCPZqxKlRadNBUshohUtXJZOgU_ztl-N_kSUfSFG6dBLM6M21beZzlwHSoT_igy6wr053qvr5i5YfhgMzqRQvCmyQjDKV7a_soRqyLPo1mQa1y-_xnvkuaKieoWR2oxhqpTa2yvtbibhEZcDT36PaY75gdWODleqYIk2gcqCxGyUeMKgejD8boDLZzJyKXsmA7wHGRp4DwFdT76P9ZimOfSwfZPA6kCZJJ1F_LA1uE7C8j1Zjajb8B5UIpnYid_PV8hdShDuVrslH5ciYdNEfgIK1v4t7gLLmFxfKRwTaZbO7Lhp1m00 "Compact Legend Layout Sample")

## LAYOUT_AS_SKETCH() and SET_SKETCH_STYLE(?bgColor, ?fontColor, ?warningColor, ?fontName, ?footerWarning, ?footerText)

C4-PlantUML can be especially helpful during up-front design sessions.
One thing which is often ignored is the fact, that these software architecture sketches are just sketches.

Without any proof

- if they are technically possible
- if they can fulfill all requirements
- if they keep what they promise

More often these sketches are used by many people as facts and are manifested into their documentations.
With `LAYOUT_AS_SKETCH()` you can make a difference.

```plantuml
@startuml LAYOUT_AS_SKETCH Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

LAYOUT_AS_SKETCH()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![LAYOUT_AS_SKETCH Sample](https://www.plantuml.com/plantuml/png/JK_BJiCm4BpdAqmvD9NQX5PmuTGGLLIYXOYa84wHaopKaX-MlI6g4F_EMfGMNrRUcTcPMNha3dibemkXMzbtmFQ8rj-cgUD3yY5mtpUz1zSQZQ0nQOrAhUGwQ6OUEocQDB-U5M6rssvI1nAu1vz-Bcwk2Abp4dAXmIKss4IRxErfLzLPMPSFgofVnvCeAi1vesFUAQ6dR9I5AJmwZiQD9b5vy0YglZEzxhWxnEryoiObLrR2UCA-8aRlP1CFqDJSMhhp2WtBh9MYvIYC7j4glvooh2oInrL54WTiaSpPzYKFM2Qb6JmBRJr3mwYgvKHHlKH1NgmQ128uXaA192zFsRwFwMBy1UdEaKPWz0pohzKvriwJakQwgegIM85qGizdxW4zVI6CTsVKVyaITDSh-GC0 "LAYOUT_AS_SKETCH Sample")

Additional styles and the footer text can be changed with SET_SKETCH_STYLE():

- `SET_SKETCH_STYLE(?bgColor, ?fontColor, ?warningColor, ?fontName, ?footerWarning, ?footerText)`:
  Enables the modification of differnt sketch styles and footer.

The possible font name(s) depend on the output format (e.g. PNG uses fonts which are installed on the server and SVG fonts have to be installed on the client).
Additional is it possible to define comma separated fall back fonts (if the diagrams are exported as SVG. Atm
PNG does not support fallback fonts based on a PlantUML [bug](https://forum.plantuml.net/14842/specify-fall-back-fonts-is-not-working), but this could be fixed in one of the following versions)

```plantuml
@startuml LAYOUT_AS_SKETCH Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

SET_SKETCH_STYLE($bgColor="lightblue", $fontColor="darkblue", $warningColor="darkred", $footerWarning="Sketch", $footerText="Created for discussion")

' PNG with font jlm_cmmi10 (typically another font is used)
' SET_SKETCH_STYLE($fontName="jlm_cmmi10")

' SVG with fallback fonts MS Gothic,Comic Sans MS, Comic Sans, Chalkboard SE, Comic Neue, cursive, sans-serif (typically without "MS Gothic")
SET_SKETCH_STYLE($fontName="MS Gothic,Comic Sans MS,Comic Sans,Chalkboard SE,Comic Neue,cursive,sans-serif")

LAYOUT_AS_SKETCH()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

PNG with font `jlm_cmmi10`

![LAYOUT_AS_SKETCH with custom style png Sample](https://www.plantuml.com/plantuml/png/VL9TQnf157ttLznk0p6mqIIqBmKXTf44cbZfRXBojCpENdNgV2mpTsAbzB_tJjHeAQqlitFFnpcNyJgGy1IDxhrJLkhO8Yo9kl1fEFHYFLWeMiOc1lJIMK9B0-dCiDF29irve5QhPbXyE9-bqSFztT2ZHX4m35-kFbumKXSi5CgY7tGffbTEghhyCgcAsxgidkyc_PDcKJZj_2ZJQh6aHaVCSZYPisutRuLVxSThuQsoYoF4OxlbEqB_j8L7MRb2aii3KE4F6cM5Hq7OmjnvQ5MGCGJbR7RMwvt2R7e3QzuNKZ9yrwQMngZB2-ZJfbDIQBq1OHqjqMyfAa0Cs9wnzk-b4cCg38woWzCsftpSvx1b8-JgrIt0VGatxAvaNZYZ99J2fc4EXoj_BuLUDKxubZFtq1GZvY2Z3-g5Fm8ppmDwDJ-kdY9T9CZUShZE_th_gyzHdJ_R79NPTpbKIRlVZP-_FbJrkDnbzdasGn-SxOlMA9j3Dawd2kG5EPyARWAXgJ-xQ5lXDtrvcSDfAKodyVGCVlQ0Vs__iFuQcrfq7ViyOGFZhjEyFAKNvb7nFeTnEHjC9nLBFCBLu1Bk7uk4ZRLswzVdz078WNIc4qmnKPFYBAZMYWWza3AeEIjmjr-xTdtQWkopewLblw7URtMezH1OoUTjLSrAPYNI6tgmkK4AVCLqpBqpnv9hj6qq-ZS0 "LAYOUT_AS_SKETCH with custom style png Sample")

SVG with fallback fonts MS Gothic,Comic Sans MS,Comic Sans,Chalkboard SE,Comic Neue,cursive,sans-serif

![LAYOUT_AS_SKETCH with custom style svg Sample](https://www.plantuml.com/plantuml/svg/VL9TQnf157ttLznk0p6mqIIqBmKXTf44cbZfRXBojCpENdNgV2mpTsAbzB_tJjHeAQqlitFFnpcNyJgGy1IDxhrJLkhO8Yo9kl1fEFHYFLWeMiOc1lJIMK9B0-dCiDF29irve5QhPbXyE9-bqSFztT2ZHX4m35-kFbumKXSi5CgY7tGffbTEghhyCgcAsxgidkyc_PDcKJZj_2ZJQh6aHaVCSZYPisutRuLVxSThuQsoYoF4OxlbEqB_j8L7MRb2aii3KE4F6cM5Hq7OmjnvQ5MGCGJbR7RMwvt2R7e3QzuNKZ9yrwQMngZB2-ZJfbDIQBq1OHqjqMyfAa0Cs9wnzk-b4cCg38woWzCsftpSvx1b8-JgrIt0VGatxAvaNZYZ99J2fc4EXoj_BuLUDKxubZFtq1GZvY2Z3-g5Fm8ppmDwDJ-kdY9T9CZUShZE_th_gyzHdJ_R79NPTpbKIRlVZP-_FbJrkDnbzdasGn-SxOlMA9j3Dawd2kG5EPyARWAXgJ-xQ5lXDtrvcSDfAKodyVGCVlQ0Vs__iFuQcrfq7ViyOGFZhjEyFAKNvb7nFeTnEHjC9nLBFCBLu1Bk7uk4ZRLswzVdz078WNIc4qmnKPFYBAZMYWWza3AeEIjmjr-xTdtQWkopewLblw7URtMezH1OoUTjLSrAPYNI6tgmkK4AVCLqpBqpnv9hj6qq-ZS0 "LAYOUT_AS_SKETCH with custom style svg Sample")

All available (PNG) fonts can be displayed with

```plantuml
@startuml
listfonts
@enduml
```

## HIDE_STEREOTYPE()

To enable a layout without `<<stereotypes>>` and legend.
This can be enabled with `HIDE_STEREOTYPE()`.

```plantuml
@startuml HIDE_STEREOTYPE Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

HIDE_STEREOTYPE()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![HIDE_STEREOTYPE Sample](https://www.plantuml.com/plantuml/png/JL1DJuD04BtpArOy598MRACNJqKariGgALJZYImmsatsOxCxI1hZVtTNQokN2VC-tfjTMgG61y63CoOxFlH0TeZQNgUfeMFopd0tj8C5qoc9837fb4Wrfz9hPXPxpjeqlvoLVhLTFwG6E50BDlrON5qufCcTa3899j4-9bZTtnPDLHURugb-BOie3e8IZ5KoehrWSah2p4zcqL1K9eo3QcyHH7EZ1jbJiu-w-PHCAYeqXqbCFWFYlcDAD4BRKAsTpmkq9DEQiuuYKp9qg_nyIhAgJ1wBsaaCa4Ko9-ldt6CPvsgqn1zh2IhIAQ6feuY18zCSI3qoH304cG3E95ZNxUlGBi9VqFaSQ0uCDi3_hZhLsbgmFczLrsKLnZ-a8tgokGEqxXVyU3DA_9SiGVRkCRy1 "HIDE_STEREOTYPE Sample")

## HIDE_PERSON_SPRITE(), SHOW_PERSON_SPRITE(?sprite), SHOW_PERSON_PORTRAIT() and SHOW_PERSON_OUTLINE()

With the macros `HIDE_PERSON_SPRITE()`, `SHOW_PERSON_SPRITE()` and `SHOW_PERSON_PORTRAIT()` it is possible to change the person related default sprite or person layout itself. `SHOW_PERSON_SPRITE()` is the default.

- **HIDE_PERSON_SPRITE()**: deactivates the default sprite
- **SHOW_PERSON_SPRITE()**: activates the default sprite "person"
- **SHOW_PERSON_SPRITE($sprite)**: activates a specific sprite as default sprite
- **SHOW_PERSON_PORTRAIT()**: activates portrait instead of a rectangle
- **SHOW_PERSON_OUTLINE()**: activates person outline instead of a rectangle

"person" and "person2" are predefined sprites which can be used as default sprite too.

```plantuml
@startuml predefined sprites Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

Person(userA, "User A", "with predefined sprite person", "person")
Person(userB, "User B", "with predefined sprite person2", "person2")
@enduml
```

![Predefined sprites Sample](https://www.plantuml.com/plantuml/png/XOwzJiOm34NtFaNu9YhH1bMmCFLd1QbBPvGsXaPAdSXswEkJ82gnCUKgFZxNFOiXIOUlxXnkFbbGkqZa5wt9dEsdapsjYO6sW08exHOE7Rt1ijEmMEzMFJqrS_bQtburWGV3mFghUtxCa_Sfe1Y7G6qiDTKCn07lYtDuKBSblsguvNJcBXK9B7nat2gEv0HK_E4By9lgluhnKep_Ahf2NB6kUa2R3_e6 "Predefined sprites Sample")

### Using HIDE_PERSON_SPRITE()

```plantuml
@startuml HIDE_PERSON_SPRITE Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

HIDE_PERSON_SPRITE()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![HIDE_PERSON_SPRITE Sample](https://www.plantuml.com/plantuml/png/JL1TJy8m57tVhwZum4XW4w8lFZ7d8YI22nlwk7JRLPhqesblNOZnlzj61FToiti-phbTMgG6dU3H5PCTTpsG0wAszsbgw91yC3ourbamdP884fDEYLHpAeDcPh7dh4tpsraPLllDSsg00xLWqy_5tOr7cbn9f4o2INI8YLRhnw8fYrtricsgShUkYtWIHIKOgsHCUy7ab8ooC9b5Gr6PqIIgZXP1D0_AoPwQOzpDfsHSKQ4vZ2VaAoB-EmV50xGDrThxl45BCgqvwoWo9KT-bLzFILQLoRQelSG0MIHpiddD0vPnhWPBmhsMe2AT4ffwYd0ScUP0we4XWY78172VPNstxrEx67z1xtEYUJ3Q0V-xwb9hxnyevAtgkgmyAv3EwCNc2T3wNmZZtIZnNx84sJl1Vm00 "HIDE_PERSON_SPRITE Sample")

### Using SHOW_PERSON_SPRITE()

```plantuml
@startuml SHOW_PERSON_SPRITE Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

/' Not needed because this is the default with sprite "person" '/
SHOW_PERSON_SPRITE()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![SHOW_PERSON_SPRITE Sample](https://www.plantuml.com/plantuml/png/JL1DRzD04BtxLmpX44TAlRI22wU6AA98DBLYbnwjjNTALjgFrSuOgqByTsP5QUlBoFi-tfkv9jQPP--gTpPCRZO8P-P4dvNAUcb-MZxFuqoOfnWO0pTJz2ev7OhcWjWuEwhznuksFDtVVbSP7Mf2Kh-kFdqGPDYBKDk0kKabfb9hE4Q6W6ZGm8YJ5dlWioMm91F1uAEU7SCYuK0fMqPO9SmKmmhMgkfkxXw6zd3gxev3rvw-zOTwKrKj5aAjZRTX2wjTcPOuQuvvjQcw9sBqmvSu1wFpKprTRc7TQPyShZVmkmBvNghM2uw3Jaby7d24NKhEJfgj592d_VijxBgsEHvwaMI4g-OIRd_i2xPpBYu4vM84747EbRHGl2na9GjwsOen0rkFJh98klrvRbVpFr1ydca2LYTq_xTwhNLFefHvq_Tj9wn2Ua5VRRuYa_nY6Oyv-hUIQmnczkul "SHOW_PERSON_SPRITE Sample")

### Using SHOW_PERSON_SPRITE(sprite)

```plantuml
@startuml SHOW_PERSON_SPRITE(sprite) Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml
!define osaPuml https://raw.githubusercontent.com/Crashedmind/PlantUML-opensecurityarchitecture2-icons/master
!include osaPuml/Common.puml
!include osaPuml/User/all.puml

SHOW_PERSON_SPRITE("osa_user_green_architect")

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![SHOW_PERSON_SPRITE(sprite) Sample](https://www.plantuml.com/plantuml/png/ZL1DRzim3BtxLsZPeIwGM6kmNNPgPWJhWBKrOdSz6ehDDWBq8P3qWc3OVn-rficmKtKHoFSUtoElYGtov5tnpeR1JIEe7NEYprgZsLVFbdVJTYB08GQ6mDKGlKxEXAnP48_ERdNzST7ariFjTutWm12G_hdyz46GlXQXiG6mIdzjHdYIIaKoZTHlSAlHq0v6RyEeNsqMCK4W62QqV30ux2p3m1F2Sc55IzeROi3pKaSxNKVlOpX6-Hzy46Tjd7k1Y_Rc_h5lrfls_gvlcystRbtEXDhdWFqp0eJ-P3sxB8e6a68eJOuwLxDL_Yqn6eueU7iW1jz_YLCO3HxAuMgkBbhZauEBI_MhKF9EnohtiErDIZBd4RPgbPApWs4RmqnQzVkvMhLDTRVkH8AWbjMLklrHPspbNDoJoY59SLHomcI4uYV7LhnKjxVCW8gj1oTU9Db-7zEL_0BAd2CjBxO1zxhLEPOSYxBVJTSrhR0owOIUntm59YaXVqyO_R-IQmYZNFeF "SHOW_PERSON_SPRITE(sprite)")

### Using SHOW_PERSON_PORTRAIT()

```plantuml
@startuml SHOW_PERSON_PORTRAIT() Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

SHOW_PERSON_PORTRAIT()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

' if a person is combined with a sprite then the rectangle layout is used again
Person(person, "Person with sprite", $sprite="person2")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![SHOW_PERSON_PORTRAIT() Sample](https://www.plantuml.com/plantuml/png/JL3VQzim47xtNt7B1d4WjTUmlGm6zK9P1sjZOdTzDB9zJGIo97IdXJ3sl--4ssPvY2nzFxxxxePO1OwJoTvfEvWu8XoPFNqfow1EnK7pCVQHC0pECbek1ZULtYYRD5V4ez5zkVrqLQUdn_kVPK23Yf3AtvlF7mNfjY9Ksc8eV8h9chlTKrVVxflTGrVlzks--j7cgoohCP2pkHedRTUmgDAfYODY5nQhh3aJuzHzSz6EAfppuNeDoqPDtk1o1NyoaDzRL7x2lbFUYyyJzb1vR_IWM3kxaAVj-pLKJLqytBOY2GYRuXhkVsqJLXdZJWIfCG4xaBfU2MMAXhLaGNlIp1Y0zOH6iaXc-_ioNSupA3ulD06p9UXdKE0nzGDDoRCNvGZ2EGf2FcX6u2FQz0S11rRs8656dLtaf8aaV7MGTg-BclqaQhxFPhEL5FamVtrTpBHD6cIFvdMzb_qy4b8gVjUsTIEiH7f3Bts-8vDSCHtFmKt_IsxGZd4o_m00 "SHOW_PERSON_PORTRAIT()")

### Using SHOW_PERSON_OUTLINE()

> This call requires PlantUML version >= v1.2021.4!

```plantuml
@startuml SHOW_PERSON_OUTLINE() Sample
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/releases/v250/C4_Container.puml

SHOW_PERSON_OUTLINE()

Person(admin, "Administrator")
System_Boundary(c1, 'Sample') {
    Container(web_app, "Web Application", "C#, ASP.NET Core 2.1 MVC", "Allows users to compare multiple Twitter timelines")
}
System(twitter, "Twitter")

' if a person is combined with a sprite then the rectangle layout is used again
Person(person, "Person with sprite", $sprite="person2")

Rel(admin, web_app, "Uses", "HTTPS")
Rel(web_app, twitter, "Gets tweets from", "HTTPS")
@enduml
```

![SHOW_PERSON_OUTLINE() Sample](https://www.plantuml.com/plantuml/png/JL3VQzim47xtNt7B1d4WjTUmlGm6pK9O1srYQcTzDB9zJGIo97IdXJ3sl--4-wDvY2nzFxxxxePO1OwZoJvesviu89oOFNqhow3EnL7pANQHCFJECbekUZUMtYYRD5V4Wz5TkVboLQMdm_rT6T2W8gJop-hhPq7QZGYLjXWAdsAo-dR_s5RRXtg_Q_U7vkxNRfiligp2GCxcQXYrNS9idKvD71IxC5jazOKOn_Q7YtPGuPBtrqkOrshq1kSB-9k1_5wJyZDshV9UV1wnWxNtHlUAjRCpUTfyNCAwhehTjX59G5WLrt3_UvEmjJ7kJ90A4x03QUkLKCPeM4iMD6VDZ05OZsWaYsIsVy_JvJo1ulDC4p2RWtu21HvJFz2KF3jH3Y2Sao3aWsO4Fg5DVn2mPsMF4cRKnKLEcaZ2LqTfzxAeoK-YfljaDbb9aK_Jr_VPH5kbGHxGlAptRJy7Gah5RvkcgeMLIA_eMv-Vo2HNJCTJSEDxoGtQ8OxcFm00 "SHOW_PERSON_OUTLINE()")
