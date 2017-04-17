---
title: "기본 Serialization | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "이진 serialization, 기본 serialization"
  - "serialization, 기본 serialization"
ms.assetid: d899d43c-335a-433e-a589-cd187192984f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 기본 Serialization
클래스를 serialize 가능하도록 만드는 가장 쉬운 방법은 다음과 같이 [Serializable](frlrfSystemSerializableAttributeClassTopic) 특성으로 표시하는 것입니다.  
  
```csharp  
[Serializable]  
public class MyObject {  
  public int n1 = 0;  
  public int n2 = 0;  
  public String str = null;  
}  
```  
  
 아래 코드 예제에서는 이 클래스의 인스턴스를 파일로 serialize하는 방법을 보여 줍니다.  
  
```csharp  
MyObject obj = new MyObject();  
obj.n1 = 1;  
obj.n2 = 24;  
obj.str = "Some String";  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Create, FileAccess.Write, FileShare.None);  
formatter.Serialize(stream, obj);  
stream.Close();  
```  
  
 이 예제에서는 이진 포맷터를 사용하여 serialization을 수행합니다.사용할 포맷터와 스트림의 인스턴스를 만든 다음 포맷터에 대해 **Serialize** 메서드를 호출하기만 하면 됩니다.serialize할 스트림과 개체가 이 호출에 매개 변수로 제공됩니다.이 예제에서는 명확하게 보여주고 있지 않지만 전용으로 표시된 변수까지 포함한 클래스의 모든 멤버 변수가 serialize됩니다.이런 면에서 이진 serialization은 public 필드만 serialize하는 [XMLSerializer 클래스](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)와 다릅니다.이진 serialization에서 멤버 변수를 제외하는 방법에 대한 자세한 내용은 [선택적 Serialization](../../../docs/framework/serialization/selective-serialization.md)을 참조하십시오.  
  
 개체를 이전 상태로 복원하는 것도 쉽습니다.먼저 읽기용 스트림과 [포맷터](frlrfSystemRuntimeSerializationFormatterClassTopic)를 만든 다음 포맷터에 개체를 deserialize하도록 지시합니다.아래 코드 예제에서 이렇게 하는 방법을 보여 줍니다.  
  
```csharp  
IFormatter formatter = new BinaryFormatter();  
Stream stream = new FileStream("MyFile.bin", FileMode.Open, FileAccess.Read, FileShare.Read);  
MyObject obj = (MyObject) formatter.Deserialize(stream);  
stream.Close();  
  
// Here's the proof.  
Console.WriteLine("n1: {0}", obj.n1);  
Console.WriteLine("n2: {0}", obj.n2);  
Console.WriteLine("str: {0}", obj.str);  
```  
  
 위에서 사용된 [BinaryFormatter](frlrfSystemRuntimeSerializationFormattersBinaryBinaryFormatterClassTopic)는 매우 효율적이며 작은 크기의 바이트 스트림을 생성합니다.이 포맷터로 serialize된 모든 개체는 해당 포맷터로 deserialize할 수 있기 때문에 .NET Framework에서 deserialize될 개체의 serialize에 이상적인 도구입니다.개체가 deserialize될 때 생성자가 호출되지 않습니다.이러한 제약 조건은 성능상의 이유로 deserialization에 적용되었습니다.하지만 이는 런타임과 개체 작성자 간의 일부 계약에 위배되며, 개발자는 개체를 serialize 가능으로 표시할 때 결과를 잘 이해해야 합니다.  
  
 이식성이 필요한 경우에는 대신 [SoapFormatter](frlrfSystemRuntimeSerializationFormattersSoapSoapFormatterClassTopic)를 사용하십시오.위의 코드에서 **BinaryFormatter**를 **SoapFormatter**로 바꾸고 위에서처럼 **Serialize** 및 **Deserialize**를 호출합니다.이 포맷터는 위에서 사용된 예제에 대해 다음 출력을 생성합니다.  
  
```  
<SOAP-ENV:Envelope  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:SOAP- ENC="http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:SOAP- ENV="http://schemas.xmlsoap.org/soap/envelope/"  
  SOAP-ENV:encodingStyle=  
  "http://schemas.microsoft.com/soap/encoding/clr/1.0"  
  "http://schemas.xmlsoap.org/soap/encoding/"  
  xmlns:a1="http://schemas.microsoft.com/clr/assem/ToFile">  
  
  <SOAP-ENV:Body>  
    <a1:MyObject id="ref-1">  
      <n1>1</n1>  
      <n2>24</n2>  
      <str id="ref-3">Some String</str>  
    </a1:MyObject>  
  </SOAP-ENV:Body>  
</SOAP-ENV:Envelope>  
```  
  
 **Serializable** 특성은 상속될 수 없습니다.`MyObject`에서 새 클래스를 파생할 때는 새 클래스도 특성으로 표시해야 하며 그렇지 않으면 serialize할 수 없습니다.예를 들어 아래 클래스의 인스턴스를 serialize하려고 할 때 `MyStuff` 형식이 serialize 가능으로 표시되지 않았음을 알리는 [SerializationException](frlrfSystemRuntimeSerializationSerializationExceptionClassTopic)이 발생합니다.  
  
```csharp  
public class MyStuff : MyObject   
{  
  public int n3;  
}  
```  
  
 **Serializable** 특성을 사용하면 편리하지만 위에서 설명한 제한 사항이 있습니다.클래스를 serialize되도록 표시하는 시점에 대한 내용은 [Serialization 지침](../../../docs/framework/serialization/serialization-guidelines.md)을 참조하십시오. 컴파일된 뒤에는 serialization을 클래스에 추가할 수 없습니다.  
  
## 참고 항목  
 [이진 Serialization](../../../docs/framework/serialization/binary-serialization.md)   
 [Remote Objects](http://msdn.microsoft.com/ko-kr/515686e6-0a8d-42f7-8188-73abede57c58)   
 [XML 및 SOAP Serialization](../../../docs/framework/serialization/xml-and-soap-serialization.md)