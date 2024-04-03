The dataset files are organized as follows :

```
├── datasets
│   ├── Transformation n
│   │   ├── Metamodels
│   │   │   ├── source_metamodel.ecore
|   |   |   ├── target_metamodel.ecore
│   │   ├── Models
│   │   │   ├── domain n
|   |   |   |   ├── source_model.xmi
|   |   |   |   ├── target_model.xmi
                ...
│   ├── Transformation n + 1
│   │   ├── Metamodels
            ...
│   │   ├── Models
            ...

```
To summarize, you can add your own dataset by following the steps below:

* (1) Create folder with the name of the transformation (eg., *Clas2Relationa*);
* (2) Add two subfolders. The first, named *Metamodels* must contain the source and the target metamodel as *.ecore* format. The second, named *Models* must contain the source and the target model instances;
* (3) Don't forget to add a kick readme.md to explain the transformation rules.