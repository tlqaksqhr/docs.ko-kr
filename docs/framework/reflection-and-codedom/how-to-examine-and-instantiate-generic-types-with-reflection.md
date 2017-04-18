---
title: "방법: 리플렉션을 사용하여 제네릭 형식 검사 및 인스턴스화 | Microsoft Docs"
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
  - "제네릭[.NET Framework], 리플렉션"
  - "리플렉션, 제네릭 형식"
ms.assetid: f93b03b0-1778-43fc-bc6d-35983d210e74
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 리플렉션을 사용하여 제네릭 형식 검사 및 인스턴스화
제네릭 형식에 대한 정보는 다른 형식에 대한 정보와 같이, 제네릭 형식을 나타내는 <xref:System.Type> 개체를 검사하여 얻습니다.  가장 큰 차이점은 제네릭 형식에는 해당 제네릭 형식 매개 변수를 나타내는 일련의 <xref:System.Type> 개체가 있다는 것입니다.  이 단원의 첫 번째 절차에서는 제네릭 형식을 검사합니다.  
  
 제네릭 형식 정의의 형식 매개 변수에 형식 인수를 바인딩하여 생성된 형식을 나타내는 <xref:System.Type> 개체를 만들 수 있습니다.  두 번째 절차에서는 이 작업에 대해 설명합니다.  
  
### 제네릭 형식과 해당 형식 매개 변수를 검사하려면  
  
1.  제네릭 형식을 나타내는 <xref:System.Type>의 인스턴스를 가져옵니다.  다음 코드에서는 C\# `typeof` 연산자\(Visual Basic의 경우 `GetType`, Visual C\+\+의 경우 `typeid`\)를 사용하여 형식을 가져옵니다.  <xref:System.Type> 개체를 가져오는 다른 방법은 <xref:System.Type> 클래스 항목을 참조하십시오.  이 절차의 나머지 부분에는 `t`라는 메서드 매개 변수에 형식이 포함되어 있습니다.  
  
     [!code-cpp[HowToGeneric#2](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#2)]
     [!code-csharp[HowToGeneric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#2)]
     [!code-vb[HowToGeneric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#2)]  
  
2.  형식이 제네릭인지 여부를 확인하려면 <xref:System.Type.IsGenericType%2A> 속성을 사용하고 형식이 제네릭 형식 정의인지 여부를 확인하려면 <xref:System.Type.IsGenericTypeDefinition%2A> 속성을 사용합니다.  
  
     [!code-cpp[HowToGeneric#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#3)]
     [!code-csharp[HowToGeneric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#3)]
     [!code-vb[HowToGeneric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#3)]  
  
3.  <xref:System.Type.GetGenericArguments%2A> 메서드를 사용하여 제네릭 형식 인수가 포함된 배열을 가져옵니다.  
  
     [!code-cpp[HowToGeneric#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#4)]
     [!code-csharp[HowToGeneric#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#4)]
     [!code-vb[HowToGeneric#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#4)]  
  
4.  각 형식 인수에 대해 <xref:System.Type.IsGenericParameter%2A> 속성을 사용하여 해당 인수가 형식 매개 변수\(예를 들어, 제네릭 형식 정의에 있음\)인지 또는 형식 매개 변수에 대해 지정된 형식\(예를 들어, 생성된 형식에 있음\)인지 여부를 확인합니다.  
  
     [!code-cpp[HowToGeneric#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#5)]
     [!code-csharp[HowToGeneric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#5)]
     [!code-vb[HowToGeneric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#5)]  
  
5.  형식 시스템의 경우 제네릭 형식 매개 변수는 일반 형식과 같이 <xref:System.Type>의 인스턴스로 표시됩니다.  다음 코드에서는 제네릭 형식 매개 변수를 나타내는 <xref:System.Type> 개체의 이름과 매개 변수 위치를 표시합니다.  매개 변수 위치는 여기에서는 그다지 중요하지 않지만 다른 제네릭 형식의 형식 인수로 사용된 형식 매개 변수를 검사할 때 보다 중요합니다.  
  
     [!code-cpp[HowToGeneric#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#6)]
     [!code-csharp[HowToGeneric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#6)]
     [!code-vb[HowToGeneric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#6)]  
  
6.  <xref:System.Type.GetGenericParameterConstraints%2A> 메서드를 사용하여 단일 배열의 모든 제약 조건을 가져옴으로써 제네릭 형식 매개 변수의 기본 형식 제약 조건과 인터페이스 제약 조건을 확인합니다.  제약 조건의 순서는 특별히 정해져 있지 않습니다.  
  
     [!code-cpp[HowToGeneric#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#7)]
     [!code-csharp[HowToGeneric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#7)]
     [!code-vb[HowToGeneric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#7)]  
  
7.  형식 매개 변수가 참조 형식이어야 하는 것과 같이 형식 매개 변수에 대한 특수 제약 조건을 확인하려면 <xref:System.Type.GenericParameterAttributes%2A> 속성을 사용합니다.  이 속성에는 다음 코드와 같이 가릴 수 있는 가변성을 나타내는 값도 포함되어 있습니다.  
  
     [!code-cpp[HowToGeneric#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#8)]
     [!code-csharp[HowToGeneric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#8)]
     [!code-vb[HowToGeneric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#8)]  
  
8.  특수 제약 조건 특성은 플래그이며 특수 제약 조건이 없음을 나타내는 동일한 플래그\(<xref:System.Reflection.GenericParameterAttributes?displayProperty=fullName>\)도 공 분산 또는 반공변성\(Contravariance\)을 나타냅니다.  그러므로 이러한 조건 중 어느 하나를 테스트하려면 적절한 마스크를 사용해야 합니다.  이 경우에는 <xref:System.Reflection.GenericParameterAttributes?displayProperty=fullName>를 사용하여 특수 제약 조건 플래그를 격리합니다.  
  
     [!code-cpp[HowToGeneric#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#9)]
     [!code-csharp[HowToGeneric#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#9)]
     [!code-vb[HowToGeneric#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#9)]  
  
## 제네릭 형식의 인스턴스 생성  
 제네릭 형식은 템플릿과 같습니다.  해당 제네릭 형식 매개 변수의 실제 형식을 지정해야 해당 인스턴스를 만들 수 있습니다.  런타임에 리플렉션을 사용하여 이 작업을 수행하려면 <xref:System.Type.MakeGenericType%2A> 메서드가 필요합니다.  
  
#### 제네릭 형식의 인스턴스를 생성하려면  
  
1.  제네릭 형식을 나타내는 <xref:System.Type> 개체를 가져옵니다.  다음 코드에서는 두 가지 다른 방법으로 <xref:System.Collections.Generic.Dictionary%602> 제네릭 형식을 가져옵니다. 즉, 형식에 대해 설명하는 문자열에 <xref:System.Type.GetType%28System.String%29?displayProperty=fullName> 메서드 오버로드를 사용하거나, 생성된 형식 `Dictionary\<String, Example>`\(Visual Basic의 경우 `Dictionary(Of String, Example)`\)에 대해 <xref:System.Type.GetGenericTypeDefinition%2A> 메서드를 호출합니다.  <xref:System.Type.MakeGenericType%2A> 메서드에는 제네릭 형식 정의가 필요합니다.  
  
     [!code-cpp[HowToGeneric#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#10)]
     [!code-csharp[HowToGeneric#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#10)]
     [!code-vb[HowToGeneric#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#10)]  
  
2.  형식 매개 변수를 대체할 형식 인수 배열을 생성합니다.  이 배열에는 올바른 수의 <xref:System.Type> 개체가 포함되어야 하며 개체 순서는 형식 매개 변수 목록에 표시되는 순서와 동일해야 합니다.  이 경우 첫 번째 형식 매개 변수인 키의 형식은 <xref:System.String>이며 사전의 값은 `Example` 클래스의 인스턴스입니다.  
  
     [!code-cpp[HowToGeneric#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#11)]
     [!code-csharp[HowToGeneric#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#11)]
     [!code-vb[HowToGeneric#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#11)]  
  
3.  <xref:System.Type.MakeGenericType%2A> 메서드를 호출하여 형식 매개 변수에 형식 인수를 바인딩하고 형식을 생성합니다.  
  
     [!code-cpp[HowToGeneric#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#12)]
     [!code-csharp[HowToGeneric#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#12)]
     [!code-vb[HowToGeneric#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#12)]  
  
4.  생성된 형식의 개체를 만들려면 <xref:System.Activator.CreateInstance%28System.Type%29> 메서드 오버로드를 사용합니다.  다음 코드에서는 결과 `Dictionary<String, Example>` 개체에 `Example` 클래스의 두 인스턴스를 저장합니다.  
  
     [!code-cpp[HowToGeneric#13](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#13)]
     [!code-csharp[HowToGeneric#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#13)]
     [!code-vb[HowToGeneric#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#13)]  
  
## 예제  
 다음 코드 예제에서는 `DisplayGenericType` 메서드를 정의하여 코드에서 사용되는 제네릭 형식 정의와 생성된 형식을 검사하고 해당 정보를 표시합니다.  `DisplayGenericType` 메서드는 <xref:System.Type.IsGenericType%2A>, <xref:System.Type.IsGenericParameter%2A> 및 <xref:System.Type.GenericParameterPosition%2A> 속성과 <xref:System.Type.GetGenericArguments%2A> 메서드를 사용하는 방법을 보여 줍니다.  
  
 이 예제에서는 또한 `DisplayGenericParameter` 메서드를 정의하여 제네릭 형식 매개 변수를 검사하고 해당 제약 조건을 표시합니다.  
  
 이 코드 예제에서는 형식 매개 변수의 제약 조건을 설명하는 제네릭 형식을 포함하여 일련의 테스트 형식을 정의하며 해당 형식에 대한 정보를 표시하는 방법을 보여 줍니다.  
  
 또한 형식 인수의 배열을 만들고 <xref:System.Type.MakeGenericType%2A> 메서드를 호출하여 <xref:System.Collections.Generic.Dictionary%602> 클래스에서 형식을 생성합니다.  이 프로그램은 <xref:System.Type.MakeGenericType%2A>을 사용하여 생성된 <xref:System.Type> 개체와 `typeof`\(Visual Basic의 경우 `GetType`\)를 사용하여 가져온 <xref:System.Type> 개체를 비교하여 동일한 개체임을 보여 줍니다.  또한 이와 유사하게 <xref:System.Type.GetGenericTypeDefinition%2A> 메서드를 사용하여 생성된 형식의 제네릭 형식 정의를 가져오고 해당 정의와 <xref:System.Collections.Generic.Dictionary%602> 클래스를 나타내는 <xref:System.Type> 개체를 비교합니다.  
  
 [!code-cpp[HowToGeneric#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HowToGeneric/cpp/ur.cpp#1)]
 [!code-csharp[HowToGeneric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToGeneric/CS/ur.cs#1)]
 [!code-vb[HowToGeneric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToGeneric/VB/ur.vb#1)]  
  
## 코드 컴파일  
  
-   이 코드에는 컴파일에 필요한 C\# `using` 문\(Visual Basic의 경우 `Imports`\)이 포함되어 있습니다.  
  
-   추가 어셈블리 참조는 필요하지 않습니다.  
  
-   csc.exe, vbc.exe 또는 cl.exe를 사용하여 명령줄에서 코드를 컴파일합니다.  Visual Studio에서 코드를 컴파일하려면 콘솔 응용 프로젝트 템플릿에 코드를 삽입합니다.  
  
## 참고 항목  
 <xref:System.Type>   
 <xref:System.Reflection.MethodInfo>   
 [리플렉션 및 제네릭 형식](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)   
 [형식 정보 보기](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)   
 [제네릭](../../../docs/standard/generics/index.md)