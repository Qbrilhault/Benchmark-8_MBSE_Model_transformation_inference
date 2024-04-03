# Class2Relational Transformation

*Clas2Relational* [1] describes the transformation of an ```object-oriented class model``` which consists of classes of type [𝐶𝑙𝑎𝑠𝑠], [𝐴𝑡𝑡𝑟𝑖𝑏𝑢𝑡𝑒] and [𝐷𝑎𝑡𝑎𝑇𝑦𝑝𝑒], into a ```relational database model``` which consists of classes of type [𝑇𝑎𝑏𝑙𝑒], [𝐶𝑜𝑙𝑢𝑚𝑛] and [𝑇𝑦𝑝𝑒].

## Characterization of the transformation rules

The characterization of the Class2Relational transformation rules below can be interpreted as follows:

* **(R1)**: Only [𝐶𝑙𝑎𝑠𝑠] classes with *𝑖𝑠𝐴𝑏𝑠𝑡𝑟𝑎𝑐𝑡* = 𝐹𝑎𝑙𝑠𝑒 are affected by the transformation. This explains the &sigma;<sub>a</sub> attribute transformation condition. The creation of a [𝑇𝑎𝑏𝑙𝑒] class inevitably leads to the creation of a [𝐶𝑜𝑙𝑢𝑚𝑛] class containing the table key and a [𝑇𝑦𝑝𝑒] class with *Integer* as the value. This explains the (c5) transformation pattern.

* **(R2)**: Classes of type [𝐷𝑎𝑡𝑎𝑇𝑦𝑝𝑒] only generate classes of type [𝑇𝑦𝑝𝑒], which corresponds to the transformationpattern (c1).

* **(R3)**: Only [𝐴𝑡𝑡𝑟𝑖𝑏𝑢𝑡𝑒] classes with *𝑚𝑢𝑙𝑡𝑖𝑉𝑎𝑙𝑢𝑒𝑑* = 𝐹𝑎𝑙𝑠𝑒 are affected by the transformation. This explains the &sigma;<sub>a</sub> attribute transformation condition. Classes of type [𝐴𝑡𝑡𝑟𝑖𝑏𝑢𝑡𝑒] only generate classes of type [𝐶𝑜𝑙𝑢𝑚𝑛], which corresponds to the transformation pattern (c1).

* **(R4)**: Only [𝐴𝑡𝑡𝑟𝑖𝑏𝑢𝑡𝑒] classes with *𝑚𝑢𝑙𝑡𝑖𝑉𝑎𝑙𝑢𝑒𝑑* = 𝑇𝑟𝑢𝑒 are affected by the transformation. This explains the &sigma;<sub>a</sub> attribute transformation condition. Since the class [𝐶𝑜𝑙𝑢𝑚𝑛], which is created from the class [𝐴𝑡𝑡𝑟𝑖𝑏𝑢𝑡𝑒], also creates a class [𝑇𝑎𝑏𝑙𝑒], a transformation pattern of type (c5) is identified.

The combination of rules (R2) and (R3) and rules (R2) and (R4) leads to patterns of type (c4) and (c6) respectively.


<img src="images/Class2Relational transformation.png" alt="class2relational" title="Class2Relational transformation rules" style="width: 50%; height: auto;">

**Table 1: Transformation rules for Class2Relational transformation**

# References
[1] Zoo ATL - https://eclipse.dev/atl/atlTransformations/#Class2Relational