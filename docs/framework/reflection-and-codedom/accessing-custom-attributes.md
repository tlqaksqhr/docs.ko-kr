---
title: "사용자 지정 특성 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "특성[.NET Framework], 액세스"
  - "사용자 지정 특성, 액세스 가능성"
  - "리플렉션, 사용자 지정 특성"
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# 사용자 지정 특성 액세스
프로그램 요소와 특성을 연결한 후 리플렉션을 사용하여 특성의 유무 및 값을 쿼리할 수 있습니다.  .NET Framework 버전 1.0 및 1.1에서 사용자 지정 특성은 실행 컨텍스트에서 검사됩니다.  .NET Framework 버전 2.0에서는 실행용으로 로드할 수 없는 코드를 검사하는 데 사용할 수 있는 새 로드 컨텍스트인 리플렉션 전용 컨텍스트를 제공합니다.  
  
## 리플렉션 전용 컨텍스트  
 리플렉션 전용 컨텍스트에 로드된 코드는 실행할 수 없습니다.  즉, 사용자 지정 특성의 인스턴스는 해당 생성자를 실행해야 하기 때문에 만들 수 없습니다.  리플렉션 전용 컨텍스트에서 사용자 지정 특성을 로드하고 검사하려면 <xref:System.Reflection.CustomAttributeData> 클래스를 사용합니다.  정적 <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=fullName> 메서드의 해당 오버로드를 사용하여 이 클래스의 인스턴스를 가져올 수 있습니다.  [방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)를 참조하십시오.  
  
## 실행 컨텍스트  
 실행 컨텍스트의 특성을 쿼리하기 위한 기본 리플렉션 메서드는 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName> 및 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>입니다.  
  
 사용자 지정 특성의 액세스 가능성은 해당 특성이 연결된 어셈블리와 관련하여 검사됩니다.  이것은 사용자 지정 특성이 연결된 어셈블리의 특정 형식에서 메서드가 사용자 지정 특성의 생성자를 호출할 수 있는지 여부를 검사하는 것과 같습니다.  
  
 <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=fullName> 같은 메서드는 형식 인수의 표시 여부와 액세스 가능성을 검사합니다.  **GetCustomAttributes**를 사용하는 형식의 사용자 지정 특성은 사용자 정의 형식을 포함하는 어셈블리의 코드에서만 검색할 수 있습니다.  
  
 다음 C\# 예제는 일반적인 사용자 지정 특성의 디자인 패턴이며,  런타임 사용자 지정 특성의 리플렉션 모델을 보여 줍니다.  
  
```  
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 런타임에서는 **GetLanguage** 메서드에 연결된 공용 사용자 지정 특성 형식인 <xref:System.ComponentModel.DescriptionAttribute>의 사용자 지정 특성을 검색할 경우 다음 작업을 수행합니다.  
  
1.  **Type.GetCustomAttributes**\(*type* 형식\)에 대한 형식 인수 **DescriptionAttribute**가 공용이어서 표시 및 액세스가 가능한지 여부를 검사합니다.  
  
2.  **DescriptionAttribute**에서 파생된 사용자 정의 형식 **MyDescriptionAttribute**가 **GetLanguage**\(\) 메서드에 연결된 **System.Web.DLL** 어셈블리 내에서 표시 및 액세스가 가능한지 여부를 검사합니다.  
  
3.  **MyDescriptionAttribute**의 생성자가 **System.Web.DLL** 어셈블리 내에서 표시 및 액세스가 가능한지 여부를 검사합니다.  
  
4.  사용자 지정 특성 매개 변수가 있는 **MyDescriptionAttribute**의 생성자를 호출하고 호출자에게 새 개체를 반환합니다.  
  
 사용자 지정 특성 리플렉션 모델은 사용자 정의 형식의 인스턴스를 해당 형식이 정의된 어셈블리 외부에 누출할 수도 있습니다.  이 모델은 **RuntimeMethodInfo** 개체의 배열을 반환하는 [Type.GetMethods\(\)](frlrfSystemTypeClassGetMethodsTopic) 같이 사용자 정의 형식의 인스턴스를 반환하는 런타임 시스템 라이브러리의 멤버와 다르지 않습니다.  사용자가 정의한 사용자 지정 특성 형식에 대한 정보를 클라이언트가 검색할 수 없도록 하려면 형식의 멤버를 비공용으로 정의합니다.  
  
 다음 예제에서는 리플렉션을 사용하여 사용자 지정 특성에 액세스하는 기본적인 방법을 보여 줍니다.  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## 참고 항목  
 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [형식 정보 보기](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [리플렉션의 보안 고려 사항](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)