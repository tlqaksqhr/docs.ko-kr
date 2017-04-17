---
title: "방법: 동적 메서드 정의 및 실행 | Microsoft Docs"
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
  - "동적 메서드"
  - "리플렉션 내보내기, 동적 메서드"
ms.assetid: 07d08a99-62c5-4254-bce2-2a75e55a18ab
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 동적 메서드 정의 및 실행
다음 절차에서는 간단한 동적 메서드와 클래스의 인스턴스에 바인딩된 동적 메서드를 정의하고 실행하는 방법을 보여 줍니다.  동적 메서드에 대한 자세한 내용은 <xref:System.Reflection.Emit.DynamicMethod> 클래스 및 [Reflection Emit Dynamic Method Scenarios](http://msdn.microsoft.com/ko-kr/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e)를 참조하십시오.  
  
### 동적 메서드를 정의하고 실행하려면  
  
1.  메서드를 실행하려면 대리자 형식을 선언해야 합니다.  선언해야 하는 대리자 형식의 수를 최소화하려면 제네릭 대리자 사용을 고려하십시오.  다음 코드에서는 `SquareIt` 메서드에 사용할 수 있는 두 개의 대리자 형식을 선언하며, 이 중 하나는 제네릭 대리자입니다.  
  
     [!code-cpp[DynamicMethodHowTo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#2)]
     [!code-csharp[DynamicMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#2)]
     [!code-vb[DynamicMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#2)]  
  
2.  동적 메서드의 매개 변수 형식을 지정하는 배열을 만듭니다.  이 예제에서는 `int`\(Visual Basic의 경우 `Integer`\)가 유일한 매개 변수이므로 배열에 하나의 요소만 있습니다.  
  
     [!code-cpp[DynamicMethodHowTo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#3)]
     [!code-csharp[DynamicMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#3)]
     [!code-vb[DynamicMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#3)]  
  
3.  <xref:System.Reflection.Emit.DynamicMethod>를 만듭니다.  이 예제에서 메서드 이름은 `SquareIt`로 지정됩니다.  
  
    > [!NOTE]
    >  동적 메서드는 이름순으로 호출할 수 없으므로 이름을 부여할 필요가 없습니다.  여러 동적 메서드는 같은 이름을 가질 수 있습니다.  그러나 이름은 호출 스택에 표시되고 디버깅하는 경우 유용할 수 있습니다.  
  
     반환 값의 형식은 `long`으로 지정됩니다.  메서드는 예제 코드가 들어 있는 `Example` 클래스를 포함하는 모듈에 연결됩니다.  임의의 로드된 모듈을 지정할 수 있습니다.  동적 메서드는 모듈 수준 `static` 메서드\(Visual Basic의 경우 `Shared`\)처럼 동작합니다.  
  
     [!code-cpp[DynamicMethodHowTo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#4)]
     [!code-csharp[DynamicMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#4)]
     [!code-vb[DynamicMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#4)]  
  
4.  메서드 본문을 내보냅니다.  이 예제에서는 <xref:System.Reflection.Emit.ILGenerator> 개체를 사용하여 MSIL\(Microsoft Intermediate Language\)을 내보냅니다.  또는 비관리 코드 생성기와 함께 <xref:System.Reflection.Emit.DynamicILInfo> 개체를 사용하여 <xref:System.Reflection.Emit.DynamicMethod>의 메서드 본문을 내보낼 수 있습니다.  
  
     이 예제에서 MSIL은 `int` 인수를 스택에 로드하고 이 인수를 `long`으로 변환하여 `long`을 복제한 다음 두 개의 수를 곱합니다.  이렇게 하면 스택에 제곱의 결과가 남고 메서드는 이 값을 반환하면 됩니다.  
  
     [!code-cpp[DynamicMethodHowTo#5](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#5)]
     [!code-csharp[DynamicMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#5)]
     [!code-vb[DynamicMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#5)]  
  
5.  <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> 메서드를 호출하여 동적 메서드를 나타내는 대리자의 인스턴스\(1단계에서 선언됨\)를 만듭니다.  대리자를 만들면 메서드가 완료되고 해당 메서드에 대한 추가 변경\(예: MSIL 계속 추가\)은 무시됩니다.  다음 코드에서는 제네릭 대리자를 사용하여 대리자를 만들고 호출합니다.  
  
     [!code-cpp[DynamicMethodHowTo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#6)]
     [!code-csharp[DynamicMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#6)]
     [!code-vb[DynamicMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#6)]  
  
### 개체에 바인딩된 동적 메서드를 정의하고 실행하려면  
  
1.  메서드를 실행하려면 대리자 형식을 선언해야 합니다.  선언해야 하는 대리자 형식의 수를 최소화하려면 제네릭 대리자 사용을 고려하십시오.  다음 코드에서는 하나의 매개 변수와 반환 값을 사용하거나, 대리자가 개체에 바인딩되어 있는 경우 두 개의 매개 변수와 하나의 반환 값을 사용하여 메서드를 실행하는 데 사용할 수 있는 제네릭 대리자 형식을 선언합니다.  
  
     [!code-cpp[DynamicMethodHowTo#12](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#12)]
     [!code-csharp[DynamicMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#12)]
     [!code-vb[DynamicMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#12)]  
  
2.  동적 메서드의 매개 변수 형식을 지정하는 배열을 만듭니다.  메서드를 나타내는 대리자가 개체에 바인딩되어 있는 경우 첫째 매개 변수는 대리자가 바인딩되어 있는 형식과 일치해야 합니다.  이 예제에서는 `Example` 형식과 `int`\(Visual Basic의 경우 `Integer`\) 형식의 두 매개 변수가 있습니다.  
  
     [!code-cpp[DynamicMethodHowTo#13](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#13)]
     [!code-csharp[DynamicMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#13)]
     [!code-vb[DynamicMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#13)]  
  
3.  <xref:System.Reflection.Emit.DynamicMethod>를 만듭니다.  이 예제에서는 메서드에 이름이 없습니다.  반환 값의 형식은 `int`\(Visual Basic의 경우 `Integer`\)로 지정됩니다.  메서드는 `Example` 클래스의 전용 멤버와 보호된 멤버에 액세스할 수 있습니다.  
  
     [!code-cpp[DynamicMethodHowTo#14](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#14)]
     [!code-csharp[DynamicMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#14)]
     [!code-vb[DynamicMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#14)]  
  
4.  메서드 본문을 내보냅니다.  이 예제에서는 <xref:System.Reflection.Emit.ILGenerator> 개체를 사용하여 MSIL\(Microsoft Intermediate Language\)을 내보냅니다.  또는 비관리 코드 생성기와 함께 <xref:System.Reflection.Emit.DynamicILInfo> 개체를 사용하여 <xref:System.Reflection.Emit.DynamicMethod>의 메서드 본문을 내보낼 수 있습니다.  
  
     이 예제에서 MSIL은 `Example` 클래스의 인스턴스인 첫째 인수를 로드하고 이 인수를 사용하여 `int` 형식의 전용 인스턴스 필드의 값을 로드합니다.  둘째 인수가 로드되고 두 개의 수를 곱합니다.  해당 결과가 `int`보다 큰 경우 값이 잘리고 최상위 비트가 삭제됩니다.  메서드가 반환되고 스택에 반환 값이 있습니다.  
  
     [!code-cpp[DynamicMethodHowTo#15](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#15)]
     [!code-csharp[DynamicMethodHowTo#15](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#15)]
     [!code-vb[DynamicMethodHowTo#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#15)]  
  
5.  <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29> 메서드 오버로드를 호출하여 동적 메서드를 나타내는 대리자의 인스턴스\(1단계에서 선언됨\)를 만듭니다.  대리자를 만들면 메서드가 완료되고 해당 메서드에 대한 추가 변경\(예: MSIL 계속 추가\)은 무시됩니다.  
  
    > [!NOTE]
    >  <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> 메서드를 여러 번 호출하여 대상 형식의 다른 인스턴스에 바인딩된 대리자를 만들 수 있습니다.  
  
     다음 코드에서는 전용 테스트 필드가 42로 설정되어 있는 `Example` 클래스의 새 인스턴스에 메서드를 바인딩합니다.  즉, 대리자를 호출할 때마다 `Example`의 인스턴스가 해당 메서드의 첫째 매개 변수로 전달됩니다.  
  
     메서드의 첫째 매개 변수가 항상 `Example`의 인스턴스를 받기 때문에 `OneParameter` 대리자를 사용합니다.  대리자를 호출할 때 둘째 매개 변수만 필요합니다.  
  
     [!code-cpp[DynamicMethodHowTo#16](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#16)]
     [!code-csharp[DynamicMethodHowTo#16](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#16)]
     [!code-vb[DynamicMethodHowTo#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#16)]  
  
## 예제  
 다음 코드 예제에서는 간단한 동적 메서드와 클래스의 인스턴스에 바인딩된 동적 메서드를 보여 줍니다.  
  
 간단한 동적 메서드는 하나의 인수인 32비트 정수를 사용하고 해당 정수의 64비트 제곱을 반환합니다.  제네릭 대리자를 사용하여 메서드를 호출합니다.  
  
 두 번째 동적 메서드에는 `Example` 형식과 `int`\(Visual Basic의 경우 `Integer`\) 형식의 두 매개 변수가 있습니다.  동적 메서드가 만들어지면 해당 메서드는 `int` 형식의 인수 하나가 있는 제네릭 대리자를 사용하여 `Example`의 인스턴스에 바인딩됩니다.  메서드의 첫째 매개 변수가 항상 `Example`의 바인딩된 인스턴스를 받기 때문에 대리자에는 `Example` 형식의 인수가 없습니다.  대리자를 호출할 때 `int` 인수만 제공됩니다.  이 동적 메서드는 `Example` 클래스의 전용 필드에 액세스하고 해당 전용 필드와 `int` 인수의 곱을 반환합니다.  
  
 이 코드 예제에서는 메서드를 실행하는 데 사용할 수 있는 대리자를 정의합니다.  
  
 [!code-cpp[DynamicMethodHowTo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#1)]
 [!code-csharp[DynamicMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#1)]
 [!code-vb[DynamicMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#1)]  
  
## 코드 컴파일  
  
-   이 코드에는 컴파일에 필요한 C\# `using` 문\(Visual Basic의 경우 `Imports`\)이 포함되어 있습니다.  
  
-   추가 어셈블리 참조는 필요하지 않습니다.  
  
-   csc.exe, vbc.exe 또는 cl.exe를 사용하여 명령줄에서 코드를 컴파일합니다.  Visual Studio에서 코드를 컴파일하려면 콘솔 응용 프로젝트 템플릿에 코드를 삽입합니다.  
  
## 참고 항목  
 <xref:System.Reflection.Emit.DynamicMethod>   
 [Using Reflection Emit](http://msdn.microsoft.com/ko-kr/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)   
 [Reflection Emit Dynamic Method Scenarios](http://msdn.microsoft.com/ko-kr/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e)