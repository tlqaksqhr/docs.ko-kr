---
title: "방법: 첫째 예외 알림 받기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "예외, 첫 번째 알림"
  - "첫째 예외 알림"
ms.assetid: 66f002b8-a97d-4a6e-a503-2cec01689113
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 첫째 예외 알림 받기
<xref:System.AppDomain> 클래스의 <xref:System.AppDomain.FirstChanceException> 이벤트를 사용하면 예외가 되었음을 알려 주는 알림을 공용 언어 런타임에서 예외 처리기 검색을 시작하기 전에 받을 수 있습니다.  
  
 이 이벤트는 응용 프로그램 도메인 수준에서 발생합니다.  실행 스레드는 여러 응용 프로그램 도메인을 통과할 수 있기 때문에 한 응용 프로그램 도메인에서 처리되지 않은 예외가 다른 응용 프로그램 도메인에서 처리될 수 있습니다.  알림은 응용 프로그램 도메인에서 예외를 처리할 때까지 이벤트 처리기가 추가된 각 응용 프로그램 도메인에서 발생합니다.  
  
 이 문서에 포함된 절차 및 예제에서는 응용 프로그램 도메인이 하나인 간단한 프로그램 및 사용자가 만든 응용 프로그램 도메인에서 첫 번째 예외 알림을 받는 방법을 보여 줍니다.  
  
 여러 응용 프로그램 도메인에 걸쳐 있는 보다 복잡한 예제를 보려면 <xref:System.AppDomain.FirstChanceException> 이벤트 예제를 참조하십시오.  
  
## 기본 응용 프로그램 도메인에서 첫 번째 예외 알림 받기  
 다음 절차에서 응용 프로그램의 진입점인 `Main()` 메서드는 기본 응용 프로그램 도메인에서 실행됩니다.  
  
#### 기본 응용 프로그램 도메인에서 첫 번째 예외 알림을 보여 주려면  
  
1.  람다 함수를 사용하여 <xref:System.AppDomain.FirstChanceException> 이벤트에 대한 이벤트 처리기를 정의하고 이를 이벤트에 연결합니다.  이 예제에서는 이벤트 처리기를 통해 이벤트가 처리된 응용 프로그램 도메인의 이름과 실행의 <xref:System.Exception.Message%2A> 속성을 출력합니다.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#2)]  
  
2.  예외를 throw하고 catch합니다.  런타임에서 예외 처리기를 찾기 전에 <xref:System.AppDomain.FirstChanceException> 이벤트가 발생하고 메시지가 표시됩니다.  이 메시지 다음에는 예외 처리기에서 표시하는 메시지가 나타납니다.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#3)]  
  
3.  예외를 throw만하고 catch하지는 않습니다.  런타임에서 예외 처리기를 찾기 전에 <xref:System.AppDomain.FirstChanceException> 이벤트가 발생하고 메시지가 표시됩니다.  예외 처리기가 없기 때문에 응용 프로그램이 종료됩니다.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#4)]  
  
     이 절차의 처음 세 단계에 나오는 코드는 그 자체로 완전한 콘솔 응용 프로그램입니다.  응용 프로그램의 출력은 .exe 파일의 이름에 따라 다를 수 있습니다. 기본 응용 프로그램 도메인의 이름은 파일 이름과 .exe 파일 확장명으로 구성되기 때문입니다.  샘플 출력은 다음을 참조하십시오.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto_simple#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto_simple/vb/example.vb#5)]  
  
## 다른 응용 프로그램 도메인에서 첫 번째 예외 알림 받기  
 프로그램에 응용 프로그램 도메인이 하나 이상 있으면 알림을 받을 응용 프로그램 도메인을 선택할 수 있습니다.  
  
#### 직접 만든 응용 프로그램 도메인에서 첫 번째 예외 알림을 받으려면  
  
1.  <xref:System.AppDomain.FirstChanceException> 이벤트에 대한 이벤트 처리기를 정의합니다.  이 예제에서는 이벤트가 처리된 응용 프로그램 도메인의 이름 및 예외의 <xref:System.Exception.Message%2A> 속성을 인쇄하는 `static` 메서드\(Visual Basic의 경우 `Shared`\)를 사용합니다.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#3)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#3)]  
  
2.  응용 프로그램 도메인을 만들고 이 응용 프로그램 도메인의 <xref:System.AppDomain.FirstChanceException> 이벤트에 대한 이벤트 처리기를 추가합니다.  이 예제에서 응용 프로그램 도메인의 이름은 `AD1`입니다.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#2)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#2)]  
  
     이 이벤트는 기본 응용 프로그램 도메인에서 동일한 방식으로 처리할 수 있습니다.  기본 응용 프로그램 도메인에 대한 참조를 가져오려면 `Main()`에서 `static`\(Visual Basic의 경우 `Shared`\) 속성인 <xref:System.AppDomain.CurrentDomain%2A?displayProperty=fullName>을 사용합니다.  
  
#### 응용 프로그램 도메인에서 첫 번째 예외 알림을 보여 주려면  
  
1.  앞 절차에서 만든 응용 프로그램 도메인에 `Worker` 개체를 만듭니다.  `Worker` 클래스는 이 문서 끝부분의 전체 예제와 같이 공용이어야 하며 <xref:System.MarshalByRefObject>에서 파생되어야 합니다.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#4)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#4)]  
  
2.  예외를 throw하는 `Worker` 개체의 메서드를 호출합니다.  이 예제에서 `Thrower` 메서드는 두 번 호출됩니다.  첫 번째 호출에서 메서드 인수는 `true`이고, 이 값은 메서드에서 자체 예외를 catch하도록 합니다.  두 번째 호출에서 메서드 인수는 `false`이고, `Main()` 메서드가 기본 응용 프로그램 도메인의 예외를 catch합니다.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#6)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#6)]  
  
3.  메서드가 자체 예외를 처리할지 여부를 제어하는 코드를 `Thrower` 메서드 내부에 작성합니다.  
  
     [!code-csharp[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#5)]
     [!code-vb[System.AppDomain.FirstChanceException_howto#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#5)]  
  
## 예제  
 다음 예제에서는 응용 프로그램 도메인 `AD1`을 만들고 이 응용 프로그램 도메인의 <xref:System.AppDomain.FirstChanceException> 이벤트에 대한 이벤트 처리기를 추가합니다.  이 예제에서는 응용 프로그램 도메인에 `Worker` 클래스의 인스턴스를 만들고, <xref:System.ArgumentException>을 throw하는 `Thrower` 메서드를 호출합니다.  인수 값에 따라서 메서드는 예외를 catch하거나 예외를 처리하지 못합니다.  
  
 `AD1`에서 `Thrower` 메서드가 예외를 throw할 때마다 `AD1`에서 <xref:System.AppDomain.FirstChanceException> 이벤트가 발생하고 이벤트 처리기에서 메시지를 표시합니다.  그런 다음 런타임이 예외 처리기를 찾습니다.  첫 번째 경우에서 예외 처리기는 `AD1`에서 찾을 수 있지만,  두 번째 경우에서는 예외가 `AD1`에서 처리되지 않고 기본 응용 프로그램 도메인에서 catch됩니다.  
  
> [!NOTE]
>  기본 응용 프로그램 도메인의 이름은 실행 파일의 이름과 동일합니다.  
  
 <xref:System.AppDomain.FirstChanceException> 이벤트 처리기를 기본 응용 프로그램 도메인에 추가하면 기본 응용 프로그램 도메인에서 해당 예외를 처리하기 전에 이 이벤트가 발생하여 처리됩니다.  이를 확인하려면 C\# 코드 `AppDomain.CurrentDomain.FirstChanceException += FirstChanceException;`\(Visual Basic의 경우 `AddHandler AppDomain.CurrentDomain.FirstChanceException, FirstChanceException`\)을 `Main()` 시작 부분에 추가합니다.  
  
 [!code-csharp[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/cs/example.cs#1)]
 [!code-vb[System.AppDomain.FirstChanceException_howto#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.firstchanceexception_howto/vb/example.vb#1)]  
  
## 코드 컴파일  
  
-   이 예제는 명령줄 응용 프로그램입니다.  이 코드를 [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)]에서 컴파일 및 실행하려면 C\# 코드 `Console.ReadLine();` \(Visual Basic의 경우 `Console.ReadLine()`\)을 `Main()` 끝부분에 추가하여 사용자가 출력을 읽기 전에 명령 창이 닫히지 않도록 합니다.  
  
## 참고 항목  
 <xref:System.AppDomain.FirstChanceException>