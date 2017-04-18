---
title: "방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의 | Microsoft Docs"
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
  - "제네릭[.NET Framework], 동적 형식"
  - "제네릭[.NET Framework], 리플렉션 내보내기"
  - "리플렉션 내보내기, 제네릭 형식"
ms.assetid: 07d5f01a-7b5b-40ea-9b15-f21561098fe4
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의
이 항목에서는 두 개의 매개 변수를 가진 간단한 제네릭 형식을 만드는 방법, 형식 매개 변수에 클래스 제약 조건, 인터페이스 제약 조건 및 특수 제약 조건을 적용하는 방법 및 클래스의 형식 매개 변수를 매개 변수 형식으로 사용하고 형식을 반환하는 멤버를 만드는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  메서드는 제네릭 형식에 속하고 해당 형식의 형식 매개 변수를 사용하므로 제네릭이 아닙니다.  메서드는 고유한 형식 매개 변수 목록이 있어야만 제네릭입니다.  제네릭 형식의 대부분의 메서드는 다음 예제와 같이 제네릭이 아닙니다.  제네릭 메서드 내보내기에 대한 예제를 보려면 [방법: 리플렉션 내보내기를 사용하여 제네릭 메서드 정의](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-method-with-reflection-emit.md)를 참조하십시오.  
  
### 제네릭 형식을 정의하려면  
  
1.  `GenericEmitExample1`이라는 이름의 동적 어셈블리를 정의합니다.  이 예제에서는 어셈블리가 실행되고 디스크에 저장되므로 <xref:System.Reflection.Emit.AssemblyBuilderAccess?displayProperty=fullName>가 지정됩니다.  
  
     [!code-cpp[EmitGenericType#2](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#2)]
     [!code-csharp[EmitGenericType#2](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#2)]
     [!code-vb[EmitGenericType#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#2)]  
  
2.  동적 모듈을 정의합니다.  어셈블리는 실행 모듈로 구성되어 있습니다.  단일 모듈 어셈블리의 경우 모듈 이름은 어셈블리 이름과 같고 파일 이름은 해당 모듈 이름에 확장명이 추가된 이름입니다.  
  
     [!code-cpp[EmitGenericType#3](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#3)]
     [!code-csharp[EmitGenericType#3](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#3)]
     [!code-vb[EmitGenericType#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#3)]  
  
3.  클래스를 정의합니다.  이 예제에서 클래스 이름은 `Sample`로 지정됩니다.  
  
     [!code-cpp[EmitGenericType#4](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#4)]
     [!code-csharp[EmitGenericType#4](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#4)]
     [!code-vb[EmitGenericType#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#4)]  
  
4.  매개 변수 이름이 포함된 문자열 배열을 <xref:System.Reflection.Emit.TypeBuilder.DefineGenericParameters%2A?displayProperty=fullName> 메서드로 전달하여 `Sample`의 제네릭 형식 매개 변수를 정의합니다.  이렇게 하면 클래스가 제네릭 형식이 됩니다.  반환 값은 형식 매개 변수를 나타내는 <xref:System.Reflection.Emit.GenericTypeParameterBuilder> 개체의 배열이며 내보낸 코드에서 사용할 수 있습니다.  
  
     다음 코드에서 `Sample`은 `TFirst` 및 `TSecond` 형식 매개 변수를 가진 제네릭 형식이 됩니다.  코드를 읽기 쉽게 만들기 위해 형식 매개 변수와 같은 이름을 사용하여 각 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>를 변수에 배치합니다.  
  
     [!code-cpp[EmitGenericType#5](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#5)]
     [!code-csharp[EmitGenericType#5](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#5)]
     [!code-vb[EmitGenericType#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#5)]  
  
5.  형식 매개 변수에 특수 제약 조건을 추가합니다.  이 예제에서 형식 매개 변수 `TFirst`는 매개 변수가 없는 생성자를 가진 형식 및 참조 형식으로 제한됩니다.  
  
     [!code-cpp[EmitGenericType#6](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#6)]
     [!code-csharp[EmitGenericType#6](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#6)]
     [!code-vb[EmitGenericType#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#6)]  
  
6.  형식 매개 변수에 클래스 제약 조건과 인터페이스 제약 조건을 선택적으로 추가합니다.  이 예제에서 형식 매개 변수 `TFirst`는 `baseType` 변수에 포함된 <xref:System.Type> 개체가 나타내는 기본 클래스에서 파생되는 형식과, 해당 형식이 `interfaceA` 변수와 `interfaceB` 변수에 포함된 인터페이스를 구현하는 형식으로 제한됩니다.  이러한 변수의 선언 및 할당에 대해서는 코드 예제를 참조하십시오.  
  
     [!code-cpp[EmitGenericType#7](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#7)]
     [!code-csharp[EmitGenericType#7](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#7)]
     [!code-vb[EmitGenericType#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#7)]  
  
7.  필드를 정의합니다.  이 예제에서 필드의 형식은 형식 매개 변수 `TFirst`에 의해 지정됩니다.  <xref:System.Reflection.Emit.GenericTypeParameterBuilder>는 <xref:System.Type>에서 파생되므로 형식을 사용할 수 있는 모든 경우에 제네릭 형식 매개 변수를 사용할 수 있습니다.  
  
     [!code-cpp[EmitGenericType#21](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#21)]
     [!code-csharp[EmitGenericType#21](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#21)]
     [!code-vb[EmitGenericType#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#21)]  
  
8.  제네릭 형식의 형식 매개 변수를 사용하는 메서드를 정의합니다.  이러한 매개 변수는 고유한 형식 매개 변수 목록이 없으면 제네릭이 아닙니다.  다음 코드에서는 `TFirst` 배열을 사용하고 해당 배열의 모든 요소가 들어 있는 `List<TFirst>`\(Visual Basic의 경우`List(Of TFirst)`\)를 반환하는 `static` 메서드\(Visual Basic의 경우 `Shared`\)를 정의합니다.  이 메서드를 정의하려면 제네릭 형식인 `List<T>`에서 <xref:System.Type.MakeGenericType%2A>을 호출하여 `List<TFirst>` 형식을 만들어야 합니다. \(`typeof` 연산자\(Visual Basic의 경우 `GetType`\)를 사용하여 제네릭 형식 정의를 가져오는 경우 `T`가 생략됩니다.\) 이 매개 변수 형식은 <xref:System.Type.MakeArrayType%2A> 메서드를 사용하여 만듭니다.  
  
     [!code-cpp[EmitGenericType#22](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#22)]
     [!code-csharp[EmitGenericType#22](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#22)]
     [!code-vb[EmitGenericType#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#22)]  
  
9. 메서드 본문을 내보냅니다.  메서드 본문은 입력 배열을 스택으로 로드하고, `IEnumerable<TFirst>`\(입력 요소를 목록에 넣는 작업을 모두 수행함\)를 사용하는 `List<TFirst>` 생성자를 호출하고, 스택에 새 <xref:System.Collections.Generic.List%601> 개체를 남겨둔 상태로 반환하는 세 개의 opcode로 구성되어 있습니다.  이 코드를 내보내는 과정에서 어려운 부분은 생성자를 가져오는 것입니다.  
  
     <xref:System.Type.GetConstructor%2A> 메서드는 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>에서 지원되지 않으므로 `List<TFirst>`의 생성자를 직접 가져올 수 없습니다.  우선 `List<T>` 제네릭 형식 정의의 생성자를 가져온 다음 `List<TFirst>`의 해당하는 생성자로 변환하는 메서드를 호출해야 합니다.  
  
     이 코드 예제에 사용된 생성자는 `IEnumerable<T>`를 사용합니다.  그러나 이 생성자는 <xref:System.Collections.Generic.IEnumerable%601> 제네릭 인터페이스의 제네릭 형식 정의가 아닙니다. `List<T>`의 형식 매개 변수 `T`를 `IEnumerable<T>`의 형식 매개 변수 `T` 대신 사용해야 합니다. \(이 방법은 양쪽 형식에 모두 `T`라는 이름의 형식 매개 변수가 있는 경우 혼란스러울 수 있습니다.  따라서 이 코드 예제에서는 `TFirst` 및 `TSecond`라는 이름을 사용합니다.\) 생성자 인수의 형식을 가져오려면 제네릭 형식 정의 `IEnumerable<T>`를 사용하여 시작하고 `List<T>`의 첫째 제네릭 형식 매개 변수를 사용하여 <xref:System.Type.MakeGenericType%2A>을 호출합니다.  생성자 인수 목록은 이 경우 하나의 인수를 가진 하나의 배열로 전달되어야 합니다.  
  
    > [!NOTE]
    >  제네릭 형식 정의는 C\#에서 `IEnumerable<>` 연산자를 사용하는 경우 `typeof`로 표현되거나, Visual Basic에서 `GetType` 연산자를 사용하는 경우 `IEnumerable(Of )`로 표현됩니다.  
  
     이제 제네릭 형식 정의에서 <xref:System.Type.GetConstructor%2A>를 호출하여 `List<T>`의 생성자를 가져올 수 있습니다.  이 생성자를 `List<TFirst>`의 해당하는 생성자로 변환하려면 `List<TFirst>` 및 해당 생성자를 `List<T>`에서 정적 <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29?displayProperty=fullName> 메서드로 전달합니다.  
  
     [!code-cpp[EmitGenericType#23](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#23)]
     [!code-csharp[EmitGenericType#23](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#23)]
     [!code-vb[EmitGenericType#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#23)]  
  
10. 형식을 만들고 파일을 저장합니다.  
  
     [!code-cpp[EmitGenericType#8](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#8)]
     [!code-csharp[EmitGenericType#8](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#8)]
     [!code-vb[EmitGenericType#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#8)]  
  
11. 메서드를 호출합니다.  `ExampleMethod`는 제네릭이 아니지만 이 메서드가 속하는 형식은 제네릭이므로 호출할 수 있는 <xref:System.Reflection.MethodInfo>를 가져오려면 형식 정의에서 `Sample`에 대한 생성된 형식을 만들어야 합니다.  생성된 형식은, 참조 형식이고 기본 매개 변수가 없는 생성자가 있기 때문에 `TFirst`에 대한 제약 조건을 충족시키는 `Example` 클래스와 `TSecond`에 대한 제약 조건을 충족시키는 `ExampleDerived` 클래스를 사용합니다. \(`ExampleDerived`의 코드는 예제 코드 섹션에서 찾을 수 있습니다.\) 이러한 두 형식을 <xref:System.Type.MakeGenericType%2A>으로 전달하여 생성된 형식을 만듭니다.  <xref:System.Type.GetMethod%2A> 메서드를 사용하여 <xref:System.Reflection.MethodInfo>를 가져옵니다.  
  
     [!code-cpp[EmitGenericType#9](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#9)]
     [!code-csharp[EmitGenericType#9](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#9)]
     [!code-vb[EmitGenericType#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#9)]  
  
12. 다음 코드에서는 `Example` 개체의 배열을 만들고, 해당 배열을 <xref:System.Object> 형식의 배열에 배치하여 호출할 메서드의 인수를 나타낸 다음 [Invoke\(Object, Object\<xref:System.Reflection.MethodBase.Invoke%28System.Object%2CSystem.Object%5B%5D%29> 메서드로 전달합니다.  <xref:System.Reflection.MethodBase.Invoke%2A> 메서드가 `static`이므로 해당 메서드의 첫째 인수는 null 참조입니다.  
  
     [!code-cpp[EmitGenericType#10](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#10)]
     [!code-csharp[EmitGenericType#10](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#10)]
     [!code-vb[EmitGenericType#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#10)]  
  
## 예제  
 다음 코드 예제에서는 기본 클래스 및 두 개의 인터페이스와 함께 `Sample`이라는 이름의 클래스를 정의합니다.  프로그램은 `Sample`에 대한 두 개의 제네릭 형식 매개 변수를 정의하고 이 클래스를 제네릭 형식으로 변환합니다.  형식 매개 변수만이 제네릭 형식을 만들 수 있습니다.  프로그램에서는 형식 매개 변수의 정의 전과 후의 테스트 메시지를 표시하여 이를 보여 줍니다.  
  
 형식 매개 변수 `TSecond`는 기본 클래스와 인터페이스를 사용하여 클래스 제약 조건과 인터페이스 제약 조건을 설명하는 데 사용되고, 형식 매개 변수 `TFirst`는 특수 제약 조건을 설명하는 데 사용됩니다.  
  
 이 코드 예제에서는 필드 형식과 매개 변수에 대한 클래스의 형식 매개 변수와 메서드의 반환 형식을 사용하여 필드와 메서드를 정의합니다.  
  
 `Sample` 클래스가 만들어진 후에 메서드가 호출됩니다.  
  
 프로그램에는 제네릭 형식에 대한 정보를 나열하는 메서드와 형식 매개 변수에 대한 특수 제약 조건을 나열하는 메서드가 포함됩니다.  이러한 메서드는 완료된 `Sample` 클래스에 대한 정보를 표시하는 데 사용됩니다.  
  
 프로그램에서 완료된 모듈을 디스크에 `GenericEmitExample1.dll`로 저장하므로 [Ildasm.exe\(IL 디스어셈블러\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 이 파일을 열고 `Sample` 클래스에 대한 MSIL을 검사합니다.  
  
 [!code-cpp[EmitGenericType#1](../../../samples/snippets/cpp/VS_Snippets_CLR/EmitGenericType/CPP/source.cpp#1)]
 [!code-csharp[EmitGenericType#1](../../../samples/snippets/csharp/VS_Snippets_CLR/EmitGenericType/CS/source.cs#1)]
 [!code-vb[EmitGenericType#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/EmitGenericType/VB/source.vb#1)]  
  
## 코드 컴파일  
  
-   이 코드에는 컴파일에 필요한 C\# `using` 문\(Visual Basic의 경우 `Imports`\)이 포함되어 있습니다.  
  
-   추가 어셈블리 참조는 필요하지 않습니다.  
  
-   csc.exe, vbc.exe 또는 cl.exe를 사용하여 명령줄에서 코드를 컴파일합니다.  Visual Studio에서 코드를 컴파일하려면 콘솔 응용 프로젝트 템플릿에 코드를 삽입합니다.  
  
## 참고 항목  
 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>   
 [Using Reflection Emit](http://msdn.microsoft.com/ko-kr/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)   
 [Reflection Emit Dynamic Assembly Scenarios](http://msdn.microsoft.com/ko-kr/e1cc6750-e20f-473b-bb4e-f43bc66aecce)