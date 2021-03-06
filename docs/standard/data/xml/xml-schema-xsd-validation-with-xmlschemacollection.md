---
title: "XML Şeması (XSD) doğrulama XmlSchemaCollection ile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ad0b5717-3d32-41ad-a4d7-072c3e492b82
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ebe8a55cd5dd80be10553948c7765f81429c0957
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="xml-schema-xsd-validation-with-xmlschemacollection"></a>XML Şeması (XSD) doğrulama XmlSchemaCollection ile
Kullanabileceğiniz <xref:System.Xml.Schema.XmlSchemaCollection> XML Şeması Tanım Dili (XSD) Şemalara karşı bir XML belgesi doğrulanacak. <xref:System.Xml.Schema.XmlSchemaCollection> Her zaman doğrulama oluşur belleğe yüklenmiş olmayan şekilde şemaları koleksiyonda depolayarak performansını artırır. Şema şema koleksiyonu varsa `schemaLocation` özniteliği şema koleksiyonundaki bakmak için kullanılır.  
  
> [!IMPORTANT]
>  <xref:System.Xml.Schema.XmlSchemaCollection> Sınıf artık kullanımdan kalkmıştır ve ile değiştirilmiştir <xref:System.Xml.Schema.XmlSchemaSet> sınıfı. Hakkında daha fazla bilgi için <xref:System.Xml.Schema.XmlSchemaSet> sınıfı bakın, [şema derleme için XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).  
  
 Aşağıdaki örnek, bir veri dosyasının kök öğesinin gösterir.  
  
```xml  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:bookstore-schema"  
    elementFormDefault="qualified"  
    targetNamespace="urn:bookstore-schema">  
```  
  
 Bu örneğin, değeri `targetNamespace` özniteliği `urn:bookstore-schema`, şemaya eklerken kullanılan aynı ad olduğu <xref:System.Xml.Schema.XmlSchemaCollection>.  
  
 Aşağıdaki kod örneğinde bir XML şeması ekler <xref:System.Xml.Schema.XmlSchemaCollection>.  
  
```vb  
Dim xsc As New XmlSchemaCollection()  
' XML Schema.  
xsc.Add("urn:bookstore-schema", schema)   
reader = New XmlTextReader(filename)  
vreader = New XmlValidatingReader(reader)  
vreader.Schemas.Add(xsc)  
```  
  
```csharp  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
// XML Schema.  
xsc.Add("urn:bookstore-schema", schema);  
reader = new XmlTextReader (filename);  
vreader = new XmlValidatingReader (reader);  
vreader.Schemas.Add(xsc);  
```  
  
 `targetNamespace` Özniteliği eklediğinizde, genellikle kullanılan `namespaceURI` özelliğinde <xref:System.Xml.Schema.XmlSchemaCollection.Add%2A> yöntemi <xref:System.Xml.Schema.XmlSchemaCollection>. Şemaya eklemeden önce bir null başvuru belirtebilirsiniz <xref:System.Xml.Schema.XmlSchemaCollection>. Boş bir dize ("") için bir ad alanı olmayan şemalarını kullanılmalıdır. <xref:System.Xml.Schema.XmlSchemaCollection> Bir ad olmadan yalnızca bir şema sahip olabilir.  
  
 Aşağıdaki kod örneğinde HeadCount.xsd, bir XML Şeması çok ekler <xref:System.Xml.Schema.XmlSchemaCollection> ve HeadCount.xml doğrular.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Schema  
  
Namespace ValidationSample  
  
   Class Sample  
  
      Public Shared Sub Main()  
         Dim tr As New XmlTextReader("HeadCount.xml")  
         Dim vr As New XmlValidatingReader(tr)  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd")  
         vr.ValidationType = ValidationType.Schema  
         AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler  
  
         While vr.Read()  
         End While  
         Console.WriteLine("Validation finished")  
      End Sub  
      ' Main  
  
      Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)  
         Console.WriteLine("***Validation error")  
         Console.WriteLine("Severity:{0}", args.Severity)  
         Console.WriteLine("Message:{0}", args.Message)  
      End Sub  
      ' ValidationHandler  
   End Class  
   ' Sample  
End Namespace  
' ValidationSample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Schema;  
  
namespace ValidationSample  
{  
   class Sample  
   {  
      public static void Main()  
      {  
         XmlTextReader tr = new XmlTextReader("HeadCount.xml");  
         XmlValidatingReader vr = new XmlValidatingReader(tr);  
  
         vr.Schemas.Add("xsdHeadCount", "HeadCount.xsd");  
         vr.ValidationType = ValidationType.Schema;  
         vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);  
  
         while(vr.Read());  
         Console.WriteLine("Validation finished");  
      }  
  
      public static void ValidationHandler(object sender, ValidationEventArgs args)  
      {  
         Console.WriteLine("***Validation error");  
         Console.WriteLine("\tSeverity:{0}", args.Severity);  
         Console.WriteLine("\tMessage  :{0}", args.Message);  
      }  
   }  
}  
```  
  
 Doğrulanacak HeadCount.xml, girdi dosyasının içeriği özetlenmektedir.  
  
```xml  
<!--Load HeadCount.xsd in SchemaCollection for Validation-->  
<hc:HeadCount xmlns:hc='xsdHeadCount'>  
   <Name>Waldo Pepper</Name>  
   <Name>Red Pepper</Name>  
</hc:HeadCount>  
```  
  
 XML Şeması dosyasının karşı doğrulanacak HeadCount.xsd, içeriği özetlenmektedir.  
  
```xml  
<xs:schema xmlns="xsdHeadCount" targetNamespace="xsdHeadCount" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name='HeadCount' type="HEADCOUNT"/>  
   <xs:complexType name="HEADCOUNT">  
      <xs:sequence>  
         <xs:element name='Name' type='xs:string' maxOccurs='unbounded'/>  
      </xs:sequence>  
      <xs:attribute name='division' type='xs:int' use='optional' default='8'/>  
   </xs:complexType>  
</xs:schema>  
```  
  
 Aşağıdaki kod örneği oluşturur bir <xref:System.Xml.XmlValidatingReader> alan bir <xref:System.Xml.XmlTextReader>. Giriş dosyası, sample4.xml, XML şemasına göre doğrulanır sample4.xsd.  
  
```vb  
Dim tr As New XmlTextReader("sample4.xml")  
Dim vr As New XmlValidatingReader(tr)  
vr.ValidationType = ValidationType.Schema  
vr.Schemas.Add("datatypesTest", "sample4.xsd")  
AddHandler vr.ValidationEventHandler, AddressOf ValidationCallBack  
While vr.Read()  
   Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name)  
End While  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("sample4.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
vr.ValidationType = ValidationType.Schema;  
        vr.Schemas.Add("datatypesTest", "sample4.xsd");  
vr.ValidationEventHandler += new ValidationEventHandler(ValidationCallBack);  
while(vr.Read()) {  
    Console.WriteLine("NodeType: {0} NodeName: {1}", vr.NodeType, vr.Name);  
    }  
```  
  
 Doğrulanacak sample4.xml, girdi dosyasının içeriği özetlenmektedir.  
  
```xml  
<datatypes xmlns="datatypesTest">  
    <number>  
        <number_1>123</number_1>  
    </number>  
</datatypes>  
```  
  
 XML Şeması dosyasının karşı doğrulanacak sample4.xsd, içeriği özetlenmektedir.  
  
```xml  
<xs:schema   
    xmlns:xs="http://www.w3.org/2001/XMLSchema"   
    xmlns:tns="datatypesTest"   
    targetNamespace="datatypesTest"  
    elementFormDefault="qualified">  
  
<xs:element name = "datatypes">  
  <xs:complexType>  
    <xs:all>  
        <xs:element name="number">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="number_1" type="xs:decimal" maxOccurs="unbounded"/>  
                </xs:sequence>  
            </xs:complexType>  
        </xs:element>  
    </xs:all>  
  </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Xml.XmlParserContext>  
 <xref:System.Xml.XmlValidatingReader.ValidationEventHandler?displayProperty=nameWithType>  
 <xref:System.Xml.XmlValidatingReader.Schemas%2A?displayProperty=nameWithType>  
 [XmlSchemaCollection şema derleme](../../../../docs/standard/data/xml/xmlschemacollection-schema-compilation.md)
