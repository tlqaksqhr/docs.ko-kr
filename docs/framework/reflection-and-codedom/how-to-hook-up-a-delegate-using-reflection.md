---
title: "방법: 리플렉션을 사용하여 대리자 후크 | Microsoft Docs"
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
  - "대리자[.NET Framework], 리플렉션을 사용하여 이벤트 처리기 추가"
  - "이벤트[.NET Framework], 리플렉션을 사용하여 이벤트 처리기 추가"
  - "리플렉션, 이벤트 처리기 대리자 추가"
ms.assetid: 076ee62d-a964-449e-a447-c31b33518b81
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 리플렉션을 사용하여 대리자 후크
리플렉션을 사용하여 어셈블리를 로드하고 실행할 때 C\# `+=` 연산자나 Visual Basic [AddHandler 문](../../../ocs/visual-basic/language-reference/statements/addhandler-statement.md)과 같은 언어 기능을 사용하여 이벤트를 후크할 수는 없습니다.  다음 절차에서는 리플렉션을 통해 필요한 모든 형식을 가져와 기존 메서드를 이벤트에 후크하는 방법과 리플렉션 내보내기를 사용하여 동적 메서드를 만들고 이벤트에 후크하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이벤트 처리 대리자를 후크하는 다른 방법은 <xref:System.Reflection.EventInfo> 클래스의 <xref:System.Reflection.EventInfo.AddEventHandler%2A> 메서드에 대한 코드 예제를 참조하십시오.  
  
### 리플렉션을 사용하여 대리자를 후크하려면  
  
1.  이벤트를 발생시키는 형식이 포함된 어셈블리를 로드합니다.  어셈블리는 일반적으로 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드와 함께 로드됩니다.  이 예제를 간단히 유지하기 위해 현재 어셈블리의 파생된 폼을 사용하므로 현재 어셈블리를 로드하는 데 <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> 메서드를 사용합니다.  
  
     [!code-cpp[HookUpDelegate#3](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#3)]
     [!code-csharp[HookUpDelegate#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#3)]
     [!code-vb[HookUpDelegate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#3)]  
  
2.  형식을 나타내는 <xref:System.Type> 개체를 가져온 다음 해당 형식의 인스턴스를 만듭니다.  폼에 기본 생성자가 있으므로 다음 코드에서는 <xref:System.Activator.CreateInstance%28System.Type%29> 메서드를 사용합니다.  만들려는 형식에 기본 생성자가 없는 경우 사용할 수 있는 <xref:System.Activator.CreateInstance%2A> 메서드의 몇 가지 다른 오버로드가 있습니다.  새 인스턴스는 <xref:System.Object> 형식으로 저장되어 어셈블리에 대해 알려진 내용이 없다는 fiction을 유지합니다. \(리플렉션을 사용하면 형식의 이름을 미리 알지 않아도 어셈블리에서 형식을 가져올 수 있습니다.\)  
  
     [!code-cpp[HookUpDelegate#4](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#4)]
     [!code-csharp[HookUpDelegate#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#4)]
     [!code-vb[HookUpDelegate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#4)]  
  
3.  이벤트를 나타내는 <xref:System.Reflection.EventInfo> 개체를 가져온 다음 <xref:System.Reflection.EventInfo.EventHandlerType%2A> 속성을 사용하여 이벤트 처리에 사용된 대리자의 형식을 가져옵니다.  다음 코드에서 <xref:System.Windows.Forms.Control.Click> 이벤트에 대해 <xref:System.Reflection.EventInfo>를 가져옵니다.  
  
     [!code-cpp[HookUpDelegate#5](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#5)]
     [!code-csharp[HookUpDelegate#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#5)]
     [!code-vb[HookUpDelegate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#5)]  
  
4.  이벤트를 처리하는 메서드를 나타내는 <xref:System.Reflection.MethodInfo> 개체를 가져옵니다.  이 항목의 뒷부분에 나오는 예제세션의 완성된 프로그램 코드는 <xref:System.EventHandler> 의 서명을 일치시키는 메서드 대리자가 포함되어있으며, 이것은 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리하지만, 실행시간에 동적 메서드를 발생시킬 수 있습니다.  절차 동적 메서드를 사용하여 실행시간에 이벤트 처리기를 생성하는 것에 대한 자세한 내용은, 다음에 나오는 프로시저를 참조하십시오.  
  
     [!code-cpp[HookUpDelegate#6](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#6)]
     [!code-csharp[HookUpDelegate#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#6)]
     [!code-vb[HookUpDelegate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#6)]  
  
5.  <xref:System.Delegate.CreateDelegate%2A> 메서드를 사용하여 대리자의 인스턴스를 만듭니다.  이 메서드는 정적\(Visual Basic의 경우 `Shared`\)이므로 대리자 형식이 제공되어야 합니다.  <xref:System.Reflection.MethodInfo>를 사용하는 <xref:System.Delegate.CreateDelegate%2A>의 오버로드를 사용하는 것이 좋습니다.  
  
     [!code-cpp[HookUpDelegate#7](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#7)]
     [!code-csharp[HookUpDelegate#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#7)]
     [!code-vb[HookUpDelegate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#7)]  
  
6.  `add` 접근자 메서드를 가져오고 이 메서드를 호출하여 이벤트에 후크합니다.  모든 이벤트에는 상위 수준 언어의 구문에서 숨겨지는 `add` 접근자와 `remove` 접근자가 있습니다.  예를 들어, C\#에서는 `+=` 연산자를 사용하여 이벤트를 후크하고 Visual Basic에서는 [AddHandler 문](../../../ocs/visual-basic/language-reference/statements/addhandler-statement.md)을 사용하여 이벤트를 후크합니다.  다음 코드에서는 <xref:System.Windows.Forms.Control.Click> 이벤트의 `add` 접근자를 가져오고 런타임에 바인딩된 호출을 사용하여 대리자 인스턴스를 전달합니다.  인수는 배열로 전달되어야 합니다.  
  
     [!code-cpp[HookUpDelegate#8](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#8)]
     [!code-csharp[HookUpDelegate#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#8)]
     [!code-vb[HookUpDelegate#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#8)]  
  
7.  이벤트를 테스트합니다.  다음 코드에서는 코드 예제에서 정의된 폼을 보여 줍니다.  해당 폼을 클릭하면 이벤트 처리기가 호출됩니다.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
<a name="procedureSection1"></a>   
### 동적 메서드를 사용하여 런타임에 이벤트 처리기를 생성하려면  
  
1.  간단한 동적 메서드와 리플렉션 내보내기를 사용하여 런타임에 이벤트 처리기 메서드를 생성할 수 있습니다.  이벤트 처리기를 생성하려면 대리자의 반환 형식과 매개 변수 형식이 필요합니다.  이러한 형식은 대리자의 `Invoke` 메서드를 검사하여 가져올 수 있습니다.  다음 코드에서는 `GetDelegateReturnType` 메서드와 `GetDelegateParameterTypes` 메서드를 사용하여 이 정보를 가져옵니다.  이러한 메서드의 코드는 이 항목의 뒷부분에 나오는 예제 단원에서 찾을 수 있습니다.  
  
     <xref:System.Reflection.Emit.DynamicMethod>의 이름을 지정할 필요가 없으므로 빈 문자열을 사용할 수 있습니다.  다음 코드에서는 마지막 인수가 동적 메서드와 현재 형식을 연결하여 대리자에게 `Example` 클래스의 모든 공용 및 전용 멤버에 대한 액세스를 부여합니다.  
  
     [!code-cpp[HookUpDelegate#9](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#9)]
     [!code-csharp[HookUpDelegate#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#9)]
     [!code-vb[HookUpDelegate#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#9)]  
  
2.  메서드 본문을 생성합니다.  이 메서드는 문자열을 로드하고, 문자열을 사용하는 <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> 메서드의 오버로드를 호출하고, 스택에서 반환 값을 팝한 다음\(처리기에 반환 형식이 없으므로\) 반환됩니다.  동적 메서드 내보내기에 대한 자세한 내용은 [방법: 동적 메서드 정의 및 실행](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md)을 참조하십시오.  
  
     [!code-cpp[HookUpDelegate#10](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#10)]
     [!code-csharp[HookUpDelegate#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#10)]
     [!code-vb[HookUpDelegate#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#10)]  
  
3.  <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> 메서드를 호출하여 동적 메서드를 완료합니다.  `add` 접근자를 사용하여 해당 이벤트의 호출 목록에 대리자를 추가합니다.  
  
     [!code-cpp[HookUpDelegate#11](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#11)]
     [!code-csharp[HookUpDelegate#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#11)]
     [!code-vb[HookUpDelegate#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#11)]  
  
4.  이벤트를 테스트합니다.  다음 코드에서는 코드 예제에서 정의된 폼을 로드합니다.  해당 폼을 클릭하면 미리 정의된 이벤트 처리기와 내보낸 이벤트 처리기가 호출됩니다.  
  
     [!code-cpp[HookUpDelegate#12](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#12)]
     [!code-csharp[HookUpDelegate#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#12)]
     [!code-vb[HookUpDelegate#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#12)]  
  
## 예제  
 다음 코드 예제에서는 리플렉션을 사용하여 기존 메서드를 이벤트에 후크하는 방법과 <xref:System.Reflection.Emit.DynamicMethod> 클래스를 사용하여 런타임에 메서드를 내보내고 이벤트에 후크하는 방법을 보여 줍니다.  
  
 [!code-cpp[HookUpDelegate#1](../../../samples/snippets/cpp/VS_Snippets_CLR/HookUpDelegate/cpp/source.cpp#1)]
 [!code-csharp[HookUpDelegate#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HookUpDelegate/cs/source.cs#1)]
 [!code-vb[HookUpDelegate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HookUpDelegate/vb/source.vb#1)]  
  
## 코드 컴파일  
  
-   이 코드에는 컴파일에 필요한 C\# `using` 문\(Visual Basic의 경우 `Imports`\)이 포함되어 있습니다.  
  
-   명령줄에서 컴파일하는 데 추가 어셈블리 참조는 필요하지 않습니다.  이 예제는 콘솔 응용 프로그램이므로 Visual Studio에서 참조를 System.Windows.Forms.dll에 추가해야 합니다.  
  
-   csc.exe, vbc.exe 또는 cl.exe를 사용하여 명령줄에서 코드를 컴파일합니다.  Visual Studio에서 코드를 컴파일하려면 콘솔 응용 프로젝트 템플릿에 코드를 삽입합니다.  
  
## 참고 항목  
 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>   
 <xref:System.Reflection.Emit.DynamicMethod>   
 <xref:System.Activator.CreateInstance%2A>   
 <xref:System.Delegate.CreateDelegate%2A>   
 [방법: 동적 메서드 정의 및 실행](../../../docs/framework/reflection-and-codedom/how-to-define-and-execute-dynamic-methods.md)   
 [리플렉션](../../../docs/framework/reflection-and-codedom/reflection.md)