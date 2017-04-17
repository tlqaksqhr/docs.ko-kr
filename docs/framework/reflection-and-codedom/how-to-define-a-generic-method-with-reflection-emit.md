---
title: "방법: 리플렉션 내보내기를 사용하여 제네릭 메서드 정의 | Microsoft Docs"
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
  - "리플렉션 내보내기, 제네릭 메서드"
ms.assetid: 93892fa4-90b3-4ec4-b147-4bec9880de2b
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 리플렉션 내보내기를 사용하여 제네릭 메서드 정의
첫 번째 절차에서는 두 가지의 형식 매개 변수를 사용하여 간단한 제네릭 메서드를 만드는 방법과 클래스 제약 조건, 인터페이스 제약 조건 및 특수 제약 조건을 해당 형식 매개 변수에 적용하는 방법을 보여 줍니다.  
  
 두 번째 절차에서는 메서드 본문을 내보내는 방법과 제네릭 메서드의 형식 매개 변수를 사용하여 제네릭 형식의 인스턴스를 만들고 해당 메서드를 호출하는 방법을 보여 줍니다.  
  
 세 번째 절차에서는 제네릭 메서드를 호출하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  메서드는 제네릭 형식에 속하고 해당 형식의 형식 매개 변수를 사용하므로 제네릭이 아닙니다.  메서드는 고유한 형식 매개 변수 목록이 있어야만 제네릭입니다.  제네릭 메서드는 다음 예제와 같이 제네릭이 아닌 형식에 나타날 수 있습니다.  제네릭 형식에 있는 제네릭이 아닌 메서드의 예제를 보려면 [방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)를 참조하십시오.  
  
### 제네릭 메서드를 정의하려면  
  
1.  상위 수준 언어를 사용하여 작성된 경우에는 시작하기 전에 제네릭 메서드가 표시되는 방식을 확인하는 것이 좋습니다.  다음 코드는 제네릭 메서드를 호출하는 코드와 함께 이 항목의 예제 코드에 포함됩니다.  메서드에는 `TInput` 및 `TOutput`의 두 가지 형식 매개 변수가 있는데, 이 중 후자는 참조 형식\(`class`\)이어야 하고 매개 변수가 없는 생성자\(`new`\)가 있어야 하며 `ICollection(Of TInput)`\(C\#의 경우 `ICollection<TInput>`\)을 구현해야 합니다.  이 인터페이스 제약 조건을 사용하면 <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=fullName> 메서드를 사용하여 이 메서드가 만드는 `TOutput` 컬렉션에 요소를 추가할 수 있습니다.  메서드에는 `TInput`의 배열인 `input`이라는 하나의 정식 매개 변수가 있습니다.  이 메서드는 형식 `TOutput`의 컬렉션을 만들고 `input`의 요소를 해당 컬렉션에 복사합니다.  
  
     [!code-csharp[GenericMethodHowTo#20](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#20)]
     [!code-vb[GenericMethodHowTo#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#20)]  
  
2.  동적 어셈블리와 동적 모듈을 정의하여 제네릭 메서드가 속하는 형식을 포함시킵니다.  이 경우 어셈블리에는 `DemoMethodBuilder1`이라는 하나의 모듈만 있고 해당 모듈 이름은 어셈블리 이름에 확장명을 추가하여 사용합니다.  이 예제에서는 어셈블리가 디스크에 저장되고 실행되므로 <xref:System.Reflection.Emit.AssemblyBuilderAccess?displayProperty=fullName>가 지정됩니다.  [Ildasm.exe\(IL 디스어셈블러\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 DemoMethodBuilder1.dll을 검사하고 이 파일과 MSIL\(Microsoft intermediate language\)에서 메서드\(1단계에 표시\)를 비교합니다.  
  
     [!code-csharp[GenericMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#2)]
     [!code-vb[GenericMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#2)]  
  
3.  제네릭 메서드가 속하는 형식을 정의합니다.  해당 형식이 제네릭일 필요는 없습니다.  제네릭 메서드는 제네릭 형식 또는 제네릭이 아닌 형식에 속할 수 있습니다.  이 예제에서는 형식이 `DemoType`이라는 이름의 클래스이며 제네릭이 아닙니다.  
  
     [!code-csharp[GenericMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#3)]
     [!code-vb[GenericMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#3)]  
  
4.  제네릭 메서드를 정의합니다.  제네릭 메서드의 정식 매개 변수 형식이 제네릭 메서드의 제네릭 매개 변수로 지정되는 경우 <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%28System.String%2CSystem.Reflection.MethodAttributes%29> 메서드 오버로드를 사용하여 해당 메서드를 정의합니다.  메서드의 제네릭 정식 매개 변수가 아직 정의되지 않은 경우 <xref:System.Reflection.Emit.TypeBuilder.DefineMethod%2A>에 대한 호출에서 해당 메서드의 형식 매개 변수의 형식을 지정할 수 없습니다.  이 예제에서 메서드 이름은 `Factory`로 지정됩니다.  메서드는 공용이고 `static`\(Visual Basic의 경우 `Shared`\)입니다.  
  
     [!code-csharp[GenericMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#4)]
     [!code-vb[GenericMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#4)]  
  
5.  매개 변수 이름이 포함된 문자열 배열을 <xref:System.Reflection.Emit.MethodBuilder.DefineGenericParameters%2A?displayProperty=fullName> 메서드로 전달하여 `DemoMethod`의 제네릭 형식 매개 변수를 정의합니다.  이렇게 하면 메서드가 제네릭 메서드가 됩니다.  다음 코드에서 `Factory`는 `TInput` 및 `TOutput` 형식 매개 변수를 가진 제네릭 메서드가 됩니다.  코드를 보다 읽기 쉽게 만들기 위해 이러한 이름을 가진 변수를 만들어 두 가지 형식 매개 변수를 나타내는 <xref:System.Reflection.Emit.GenericTypeParameterBuilder> 개체를 유지합니다.  
  
     [!code-csharp[GenericMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#5)]
     [!code-vb[GenericMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#5)]  
  
6.  형식 매개 변수에 특수 제약 조건을 선택적으로 추가합니다.  <xref:System.Reflection.Emit.GenericTypeParameterBuilder.SetGenericParameterAttributes%2A> 메서드를 사용하여 특수 제약 조건을 추가합니다.  이 예제에서는 `TOutput`을 참조 형식으로 제한하고 매개 변수가 없는 생성자를 갖도록 제한합니다.  
  
     [!code-csharp[GenericMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#6)]
     [!code-vb[GenericMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#6)]  
  
7.  형식 매개 변수에 클래스 제약 조건과 인터페이스 제약 조건을 선택적으로 추가합니다.  이 예제에서는 형식 매개 변수 `TOutput`을 `ICollection(Of TInput)`\(C\#의 경우 `ICollection<TInput>`\) 인터페이스를 구현하는 형식으로 제한합니다.  이렇게 하면 <xref:System.Collections.Generic.ICollection%601.Add%2A> 메서드를 사용하여 요소를 추가할 수 있습니다.  
  
     [!code-csharp[GenericMethodHowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#7)]
     [!code-vb[GenericMethodHowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#7)]  
  
8.  <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A> 메서드를 사용하여 메서드의 정식 매개 변수를 정의합니다.  이 예제에서 `Factory` 메서드에는 `TInput`의 배열인 하나의 매개 변수가 있습니다.  이 형식은 `TInput`을 나타내는 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>에서 <xref:System.Type.MakeArrayType%2A> 메서드를 호출하여 만듭니다.  <xref:System.Reflection.Emit.MethodBuilder.SetParameters%2A>의 인수는 <xref:System.Type> 개체의 배열입니다.  
  
     [!code-csharp[GenericMethodHowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#8)]
     [!code-vb[GenericMethodHowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#8)]  
  
9. <xref:System.Reflection.Emit.MethodBuilder.SetReturnType%2A> 메서드를 사용하여 메서드의 반환 형식을 정의합니다.  이 예제에서는 `TOutput`의 인스턴스가 반환됩니다.  
  
     [!code-csharp[GenericMethodHowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#9)]
     [!code-vb[GenericMethodHowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#9)]  
  
10. <xref:System.Reflection.Emit.ILGenerator>를 사용하여 메서드 본문을 내보냅니다.  메서드 본문을 내보는 것에 대한 자세한 내용은, 다음에 나오는 프로시저를 참조하십시오.  
  
    > [!IMPORTANT]
    >  제네릭 형식의 메서드에 대한 호출을 내보내고 해당 형식의 형식 인수가 제네릭 메서드의 형식 매개 변수인 경우 <xref:System.Reflection.Emit.TypeBuilder> 클래스의 `static` <xref:System.Reflection.Emit.TypeBuilder.GetConstructor%28System.Type%2CSystem.Reflection.ConstructorInfo%29>, <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29>, and <xref:System.Reflection.Emit.TypeBuilder.GetField%28System.Type%2CSystem.Reflection.FieldInfo%29> 메서드 오버로드를 사용하여 해당 메서드의 생성된 폼을 가져와야 합니다.  메서드 본문 내보내기에 수반되는 절차에서 이 작업에 대해 설명합니다.  
  
11. 메서드가 포함된 형식을 완료하고 어셈블리를 저장합니다.  제네릭 메서드를 호출하는 것에 대한 다음 프로시저는 완성된 메서드를 호출하는 두 가지 방법을 보여 줍니다.  
  
     [!code-csharp[GenericMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#14)]
     [!code-vb[GenericMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#14)]  
  
<a name="procedureSection1"></a>   
### 메서드 본문을 내보내려면  
  
1.  코드 생성기를 가져오고 지역 변수와 레이블을 선언합니다.  <xref:System.Reflection.Emit.ILGenerator.DeclareLocal%2A> 메서드는 지역 변수를 선언하는 데 사용됩니다.  메서드에 의해 반환되는 새 `TOutput`을 보유하는 `retVal`, `TOutput`이  `ICollection(Of TInput)`\(C\#의 경우 `ICollection<TInput>`\)으로 캐스팅될 때 이를 보유하는 `ic`, `TInput` 개체의 입력 배열을 보유하는 `input` 및 배열을 통해 반복되는 `index`의 네 가지 지역 변수가 `Factory` 메서드에 있습니다.  또한 이 메서드에는 루프에 들어가는\(`enterLoop`\) 레이블과 루프 위쪽\(`loopAgain`\)에 사용되는 레이블이 있습니다. 이러한 레이블은 <xref:System.Reflection.Emit.ILGenerator.DefineLabel%2A> 메서드를 사용하여 정의합니다.  
  
     메서드가 맨 처음 수행하는 작업은 <xref:System.Reflection.Emit.OpCodes.Ldarg_0> opcode를 사용하여 인수를 로드하고 <xref:System.Reflection.Emit.OpCodes.Stloc_S> opcode를 사용하여 지역 변수 `input`에 해당 인수를 저장하는 것입니다.  
  
     [!code-csharp[GenericMethodHowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#10)]
     [!code-vb[GenericMethodHowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#10)]  
  
2.  <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> 메서드의 제네릭 메서드 오버로드를 사용하여 코드를 내보내고 `TOutput`의 인스턴스를 만듭니다.  이 오버로드를 사용하려면 지정된 형식에 매개 변수가 없는 생성자가 있어야 하는데, 이를 위해 제약 조건을 `TOutput`에 추가합니다.  `TOutput`을 <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A>에 전달하여 생성된 제네릭 메서드를 만듭니다.  메서드를 호출하기 위해 코드를 내보낸 다음 <xref:System.Reflection.Emit.OpCodes.Stloc_S>를 사용하여 지역 변수 `retVal`에 저장하도록 코드를 내보냅니다.  
  
     [!code-csharp[GenericMethodHowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#11)]
     [!code-vb[GenericMethodHowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#11)]  
  
3.  코드를 내보 새 `TOutput` 개체를 `ICollection(Of TInput)`에 캐스팅하고 해당 코드를 지역 변수 `ic`에 저장합니다.  
  
     [!code-csharp[GenericMethodHowTo#31](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#31)]
     [!code-vb[GenericMethodHowTo#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#31)]  
  
4.  <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=fullName> 메서드를 나타내는 <xref:System.Reflection.MethodInfo>를 가져옵니다.  이 메서드는 `ICollection(Of TInput)`\(C\#의 경우 `ICollection<TInput>`\)에서 작동하므로 해당 생성된 형식에 적용되는 `Add` 메서드를 가져와야 합니다.  <xref:System.Type.GetMethod%2A> 메서드는 <xref:System.Reflection.Emit.GenericTypeParameterBuilder>를 사용하여 생성된 형식에서 지원되지 않기 때문에 <xref:System.Type.GetMethod%2A> 메서드를 사용하여 `icollOfTInput`에서 이 <xref:System.Reflection.MethodInfo>를 직접 가져올 수 없습니다.  대신 <xref:System.Collections.Generic.ICollection%601> 제네릭 인터페이스에 대한 제네릭 형식 정의가 들어 있는 `icoll`에서 <xref:System.Type.GetMethod%2A>를 호출합니다.  그런 다음 <xref:System.Reflection.Emit.TypeBuilder.GetMethod%28System.Type%2CSystem.Reflection.MethodInfo%29> `static` 메서드를 사용하여 생성된 형식에 대한 <xref:System.Reflection.MethodInfo>를 만듭니다.  다음 코드에서는 이 작업에 대해 설명합니다.  
  
     [!code-csharp[GenericMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#12)]
     [!code-vb[GenericMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#12)]  
  
5.  32비트 정수 0을 로드하고 이 값을 변수에 저장하는 방식으로 코드를 내보내 `index` 변수를 초기화합니다.  코드를 내보내 `enterLoop` 레이블로 분기합니다.  이 레이블은 루프 안에 있으므로 아직 표시되지 않습니다.  루프에 대한 코드는 다음 단계에서 내보냅니다.  
  
     [!code-csharp[GenericMethodHowTo#32](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#32)]
     [!code-vb[GenericMethodHowTo#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#32)]  
  
6.  루프에 대한 코드를 내보냅니다.  첫 단계는 `loopAgain` 레이블을 사용하여 <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A>을 호출하여 루프의 위쪽을 표시하는 것입니다.  레이블을 사용하는 분기문이 이제 코드 안의 이 지점으로 분기합니다.  다음 단계는 `ICollection(Of TInput)`에 캐스팅된 `TOutput` 개체를 스택으로 푸시하는 것입니다.  이 작업은 즉시 수행할 필요는 없으나 `Add` 메서드를 호출하기 위해서는 제대로 수행되어야 합니다.  그 다음 단계로 입력 배열을 스택으로 푸시한 다음 현재 인덱스가 들어 있는 `index` 변수를 배열로 푸시합니다.  <xref:System.Reflection.Emit.OpCodes.Ldelem> opcode는 스택에서 인덱스와 배열을 팝하고 인덱싱된 배열 요소를 스택으로 푸시합니다.  스택에서 컬렉션과 새 요소를 팝하고 해당 요소를 컬렉션에 추가하여 스택이 <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=fullName> 메서드를 호출할 준비가 완료되었습니다.  
  
     루프의 나머지 코드에서는 인덱스를 증가시키고 루프가 완료되었는지 여부를 확인합니다. 합계는 스택에 남겨둔 상태로 인덱스와 32비트 정수 1을 스택으로 푸시하고 추가합니다. 합계는 `index`에 저장됩니다.  <xref:System.Reflection.Emit.ILGenerator.MarkLabel%2A>이 호출되어 이 지점을 루프의 진입점으로 설정합니다.  인덱스가 다시 로드됩니다.  입력 배열이 스택으로 푸시되고 길이를 가져오기 위해 <xref:System.Reflection.Emit.OpCodes.Ldlen>이 내보내집니다.  이제 스택에 인덱스와 길이가 있고 이 둘을 비교하기 위해 <xref:System.Reflection.Emit.OpCodes.Clt>가 내보내집니다.  인덱스가 길이보다 짧은 경우 <xref:System.Reflection.Emit.OpCodes.Brtrue_S>가 루프의 시작으로 다시 분기합니다.  
  
     [!code-csharp[GenericMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#13)]
     [!code-vb[GenericMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#13)]  
  
7.  코드를 내보내 `TOutput` 개체를 스택으로 푸시하고 메서드에서 반환합니다.  지역 변수 `retVal` 및 `ic`에는 모두 새 `TOutput`에 대한 참조가 들어 있습니다. `ic`는 <xref:System.Collections.Generic.ICollection%601.Add%2A?displayProperty=fullName> 메서드에 액세스할 때만 사용됩니다.  
  
     [!code-csharp[GenericMethodHowTo#33](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#33)]
     [!code-vb[GenericMethodHowTo#33](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#33)]  
  
<a name="procedureSection2"></a>   
### 제네릭 메서드를 호출하려면  
  
1.  `Factory`는 제네릭 메서드 정의입니다.  호출하려면 해당 제네릭 형식 매개 변수에 형식을 할당해야 합니다.  이 작업을 수행하려면 <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> 메서드를 사용합니다.  다음 코드에서는 `TInput`에 <xref:System.String>을 지정하고 `TOutput`에 `List(Of String)`\(C\#의 경우 `List<string>`\)를 지정하여 생성된 제네릭 메서드를 만든 다음 해당 메서드에 대한 문자열 표현을 표시합니다.  
  
     [!code-csharp[GenericMethodHowTo#21](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#21)]
     [!code-vb[GenericMethodHowTo#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#21)]  
  
2.  런타임에 바인딩된 메서드를 호출하려면 <xref:System.Reflection.MethodBase.Invoke%2A> 메서드를 사용합니다.  다음 코드에서는 유일한 요소로서 문자열의 배열을 포함하는 <xref:System.Object>의 배열을 만들고 이 배열을 제네릭 메서드의 인수 목록으로 전달합니다.  메서드가 `static`이므로 <xref:System.Reflection.MethodBase.Invoke%2A>의 첫 매개 변수는 null 참조입니다.  반환 값은 `List(Of String)`에 캐스팅되고 해당 요소가 표시됩니다.  
  
     [!code-csharp[GenericMethodHowTo#22](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#22)]
     [!code-vb[GenericMethodHowTo#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#22)]  
  
3.  대리자를 사용하여 메서드를 호출하려면 생성된 제네릭 메서드의 시그니처와 일치하는 대리자가 있어야 합니다.  이를 위한 쉬운 방법은 제네릭 대리자를 만드는 것입니다.  다음 코드에서는 <xref:System.Delegate.CreateDelegate%28System.Type%2CSystem.Reflection.MethodInfo%29?displayProperty=fullName> 메서드 오버로드를 사용하여 예제 코드에서 정의된 제네릭 대리자 `D`의 인스턴스를 만든 다음 해당 대리자를 호출합니다.  대리자가 런타임에 바인딩된 호출보다 역할을 더 잘 수행합니다.  
  
     [!code-csharp[GenericMethodHowTo#23](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#23)]
     [!code-vb[GenericMethodHowTo#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#23)]  
  
4.  내보낸 메서드는 저장된 어셈블리를 참조하는 프로그램에서 호출할 수도 있습니다.  
  
## 예제  
 다음 코드 예제에서는 제네릭 메서드 `Factory`를 사용하여 제네릭이 아닌 형식 `DemoType`을 만듭니다.  이 메서드에는 입력 형식을 지정하는 `TInput`과 출력 형식을 지정하는 `TOutput`의 두 가지 제네릭 형식 매개 변수가 있습니다.  `TOutput` 형식 매개 변수는 `ICollection<TInput>`\(Visual Basic의 경우 `ICollection(Of TInput)`\)을 구현하도록 제한되고, 참조 형식으로 제한되고, 매개 변수가 없는 생성자를 갖도록 제한됩니다.  
  
 이 메서드에는 `TInput`의 배열인 하나의 정식 매개 변수가 있습니다.  이 메서드는 입력 배열의 모든 요소가 들어 있는 `TOutput`을 반환합니다.  `TOutput`은 <xref:System.Collections.Generic.ICollection%601> 제네릭 인터페이스를 구현하는 임의의 제네릭 컬렉션 형식이 될 수 있습니다.  
  
 코드를 실행할 때 동적 어셈블리는 DemoGenericMethod1.dll으로 저장되고 [Ildasm.exe\(IL 디스어셈블러\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 검사할 수 있습니다.  
  
> [!NOTE]
>  코드를 내보내는 방법을 배우려면 내보내려는 작업을 수행하는 Visual Basic, C\# 또는 Visual C\+\+ 프로그램을 작성한 다음 디스어셈블러를 사용하여 컴파일러에서 만든 MSIL을 검사해 보는 것이 좋습니다.  
  
 코드 예제에는 내보낸 메서드에 해당하는 소스 코드가 포함되어 있습니다.  내보낸 메서드는 런타임에 바인딩되어 호출되고 코드 예제에서 선언한 제네릭 대리자를 사용하여 호출됩니다.  
  
 [!code-csharp[GenericMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GenericMethodHowTo/CS/source.cs#1)]
 [!code-vb[GenericMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GenericMethodHowTo/VB/source.vb#1)]  
  
## 코드 컴파일  
  
-   이 코드에는 컴파일에 필요한 C\# `using` 문\(Visual Basic의 경우 `Imports`\)이 포함되어 있습니다.  
  
-   추가 어셈블리 참조는 필요하지 않습니다.  
  
-   csc.exe, vbc.exe 또는 cl.exe를 사용하여 명령줄에서 코드를 컴파일합니다.  Visual Studio에서 코드를 컴파일하려면 콘솔 응용 프로젝트 템플릿에 코드를 삽입합니다.  
  
## 참고 항목  
 <xref:System.Reflection.Emit.MethodBuilder>   
 [방법: 리플렉션 내보내기를 사용하여 제네릭 형식 정의](../../../docs/framework/reflection-and-codedom/how-to-define-a-generic-type-with-reflection-emit.md)