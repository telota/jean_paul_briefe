## Schema
#### Struktur
```
schema/
    ├── documentation/
    │        ├──html/
    │        │   ├── metadaten.html
    │        │   ├── umfeldbriefe.html
    │        │   └── von-Briefe.html
    │        └──pdf/
    │            ├── schema_metadaten.pdf
    │            ├── schema_umfeldbriefe.pdf
    │            └── schema_von-Briefe.pdf
    └── odd/
         ├── metadaten.odd
         ├── umfeldbriefe.odd
         └── von-Briefe.odd
```

### Workflow
- __teiHeader__: eine 'Mother ODD' (`metadaten.odd`) wurde gebaut. Alle verwendete Modulen sind mit einem `moduleRef`deklariert und deren Elements in `@include` erklärt. In diesen `moduleRef/@include` findet man alle Elementen der ganzen Edition, d.h. die Elementen von teiHeader und body von den von-Briefe und Umfeldbriefe. Die Elementen der teiHeader sind in dieser `metadaten.odd` angepasst, mit einem `elementSpec`. Diese ODD wurde kompiliert, um in den `body`-ODD verknüpft zu sein. 
- __body__ (`von-Briefe.odd` und `umfeldbriefe.odd`): Die kompilierte ODD der Metadaten ist in `schemaSpec\@source` der body-ODDs referenziert. In `moduleRef` finden wir die `teiHeader`-Elementen und die Elemente des spezifischen `body`s. Also für die von-Briefe findet man in `moduleRef` alle Elementen des teiHeaders und die Elementen, die spezifisch für das von-Briefes `body`. In diesen ODD sind die `teiHeader`-Element nicht angepasst, da sie schon in der `metadaten.odd` eingeschränkt wurde. Jedes angepasste `body`-Element sind mit einem `elementSpec` detailliert. Das Schema der Umfeldbriefe (`umfeldbriefe.odd`) wurde mit dem gleichen Prozess bearbeitet. 

Ein RNG wurde von den `von-Briefe.odd` und `umfeldbriefe.odd` generiert. Damit wurden die Briefe validiert. 

### Dokumentation
⚠️ _Die Dokumentation ist noch in Bearbeitungsprozess._
Für jede ODD sind Dokumentationsdateien verfügbar in zwei Formaten (`pdf` und `html`). 


