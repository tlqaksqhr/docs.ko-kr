---
title: "형식 정보 보기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "리플렉션, 형식 정보 보기"
  - "Type 개체"
  - "형식, 형식 정보 보기"
  - "형식 정보 보기"
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 형식 정보 보기
<xref:System.Type?displayProperty=fullName> 클래스는 리플렉션의 중심적인 요소입니다.  공용 언어 런타임에서는 리플렉션에서 요청할 때 로드된 형식의 **Type**을 만듭니다.  **Type** 개체의 메서드, 필드, 속성 및 중첩 클래스를 사용하여 해당 형식에 대한 모든 정보를 검색할 수 있습니다.  
  
 로드되지 않은 어셈블리에서 **Type** 개체를 가져오려면 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> 또는 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName>를 사용합니다. 이때 원하는 형식의 이름을 전달합니다.  이미 로드된 어셈블리에서 **Type** 개체를 가져오려면 <xref:System.Type.GetType%2A?displayProperty=fullName>을 사용합니다.  모듈 **Type** 개체를 가져오려면 <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName> 및 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName>를 사용합니다.  
  
> [!NOTE]
>  제네릭 형식과 메서드를 검사하고 조작하려면 [리플렉션 및 제네릭 형식](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md) 및 [방법: 리플렉션을 사용하여 제네릭 형식 검사 및 인스턴스화](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md)에서 제공하는 추가 정보를 참조하십시오.  
  
 다음 예제에서는 <xref:System.Reflection.Assembly> 개체와 어셈블리의 모듈을 가져오는 데 필요한 구문을 보여 줍니다.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 다음 예제에서는 로드된 어셈블리에서 **Type** 개체를 가져오는 방법을 보여 줍니다.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 **Type**을 가져오고 나면 여러 가지 방법으로 해당 형식의 멤버에 대한 정보를 검색할 수 있습니다.  예를 들어, <xref:System.Type.GetMembers%2A?displayProperty=fullName> 메서드를 호출하여 모든 형식의 멤버에 대한 정보를 찾을 수 있습니다. 이 메서드는 현재 형식의 각 멤버를 설명하는 <xref:System.Reflection.MemberInfo> 개체의 배열을 가져옵니다.  
  
 **Type** 클래스의 메서드를 사용하면 이름으로 지정한 하나 이상의 생성자, 메서드, 이벤트, 필드 또는 속성에 대한 정보를 검색할 수도 있습니다.  예를 들어, <xref:System.Type.GetConstructor%2A?displayProperty=fullName>는 현재 클래스의 특정 생성자를 캡슐화합니다.  
  
 **Type**이 있는 경우 <xref:System.Type.Module%2A?displayProperty=fullName> 속성을 사용하여 해당 형식이 포함된 모듈을 캡슐화하는 개체를 가져올 수 있습니다.  이 모듈이 포함된 어셈블리를 캡슐화하는 개체를 찾으려면 <xref:System.Reflection.Module.Assembly%2A?displayProperty=fullName> 속성을 사용합니다.  <xref:System.Type.Assembly%2A?displayProperty=fullName> 속성을 사용하면 형식을 캡슐화하는 어셈블리를 곧바로 가져올 수 있습니다.  
  
## System.Type 및 ConstructorInfo  
 다음 예제에서는 클래스\(이 예제에서는 <xref:System.String> 클래스\)의 생성자를 나열하는 방법을 보여 줍니다.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## MemberInfo, MethodInfo, FieldInfo 및 PropertyInfo  
 Obtain information about the type's methods, properties, events, and fields using <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> 또는 <xref:System.Reflection.PropertyInfo> 개체를 사용하여 형식의 메서드, 속성, 이벤트 및 필드에 대한 정보를 가져올 수 있습니다.  
  
 다음 예제에서는 **MemberInfo**를 사용하여 **System.IO.File** 클래스에 있는 멤버 수를 나열하고 [System.Type.IsPublic](frlrfSystemTypeClassIsPublicTopic) 속성을 사용하여 클래스의 표시 여부를 확인합니다.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 다음 예제에서는 지정된 멤버의 형식을 조사합니다.  또한 **MemberInfo** 클래스의 멤버에 대해 리플렉션을 수행하고 해당 멤버의 형식을 나열합니다.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 다음 예제에서는 모든 리플렉션 **\*Info** 클래스를 <xref:System.Reflection.BindingFlags>와 함께 사용하여 지정된 클래스의 모든 멤버\(생성자, 필드, 속성, 이벤트 및 메서드\)를 나열하고 멤버를 정적 및 인스턴스 범주로 분류합니다.  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## 참고 항목  
 <xref:System.Reflection.BindingFlags>   
 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Type.GetType%2A?displayProperty=fullName>   
 <xref:System.Type.GetMembers%2A?displayProperty=fullName>   
 <xref:System.Type.GetFields%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetType%2A?displayProperty=fullName>   
 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=fullName>   
 <xref:System.Reflection.MemberInfo>   
 <xref:System.Reflection.ConstructorInfo>   
 <xref:System.Reflection.MethodInfo>   
 <xref:System.Reflection.FieldInfo>   
 <xref:System.Reflection.EventInfo>   
 <xref:System.Reflection.ParameterInfo>   
 [리플렉션 및 제네릭 형식](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)