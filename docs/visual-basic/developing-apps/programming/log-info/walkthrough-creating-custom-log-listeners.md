---
title: "Walkthrough: Creating Custom Log Listeners (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "custom log listeners"
  - "My.Application.Log object, custom log listeners"
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Walkthrough: Creating Custom Log Listeners (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 연습에서는 사용자 지정 로그 수신기를 만들고 이를 `My.Application.Log` 개체의 출력을 수신하도록 구성하는 방법을 보여 줍니다.  
  
## 시작  
 로그 수신기는 <xref:System.Diagnostics.TraceListener> 클래스에서 상속해야 합니다.  
  
#### 수신기를 만들려면  
  
-   응용 프로그램에서, <xref:System.Diagnostics.TraceListener>에서 상속하는 `SimpleListener`라는 이름의 클래스를 만듭니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#16](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/visualbasic/VbVbalrMyApplicationLog/Form1.vb#16)]  
  
     기본 클래스에 필요한 <xref:System.Diagnostics.TraceListener.Write%2A> 및 <xref:System.Diagnostics.TraceListener.WriteLine%2A> 메서드는 `MsgBox`를 호출하여 입력을 표시합니다.  
  
     특성이 기본 클래스 메서드와 일치하도록 <xref:System.Diagnostics.TraceListener.Write%2A> 및 <xref:System.Diagnostics.TraceListener.WriteLine%2A> 메서드에 <xref:System.Security.Permissions.HostProtectionAttribute> 특성이 적용됩니다.  코드를 실행하는 호스트는 <xref:System.Security.Permissions.HostProtectionAttribute> 특성을 통해 코드에서 호스트 보호 동기화를 노출하도록 결정합니다.  
  
    > [!NOTE]
    >  <xref:System.Security.Permissions.HostProtectionAttribute> 특성은 공용 언어 런타임을 호스팅하고 SQL Server와 같은 호스트 보호를 구현하는 관리되지 않는 응용 프로그램에만 유효합니다.  
  
 `My.Application.Log`에서 로그 수신기를 사용하도록 하려면 로그 수신기가 포함된 어셈블리에 강력한 이름을 지정해야 합니다.  
  
 다음 절차에서는 강력한 이름의 로그 수신기 어셈블리를 만드는 간단한 단계를 제공합니다.  자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)을 참조하십시오.  
  
#### 로그 수신기 어셈블리에 강력한 이름을 지정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.  
  
2.  **서명** 탭을 클릭합니다.  
  
3.  **어셈블리 서명** 상자를 선택합니다.  
  
4.  **강력한 이름 키 파일 선택** 드롭다운 목록에서 **\<새로 만들기\>**를 선택합니다.  
  
     **강력한 이름 키 만들기** 대화 상자가 열립니다.  
  
5.  **키 파일 이름** 상자에 키 파일의 이름을 지정합니다.  
  
6.  **암호 입력** 및 **암호 확인** 상자에 암호를 입력합니다.  
  
7.  **확인**을 클릭합니다.  
  
8.  응용 프로그램을 다시 빌드합니다.  
  
## 수신기 추가  
 이제 어셈블리에 강력한 이름이 지정되었으므로 `My.Application.Log`에서 로그 수신기를 사용하도록 수신기의 강력한 이름을 결정해야 합니다.  
  
 강력한 이름 형식은 다음과 같은 형식을 같습니다.  
  
 \<type name\>, \<assembly name\>, \<version number\>, \<culture\>, \<strong name\>  
  
#### 수신기의 강력한 이름을 확인하려면  
  
-   다음 코드에서는 `SimpleListener`의 강력한 이름 형식의 이름을 확인하는 방법을 보여 줍니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#17](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/visualbasic/VbVbalrMyApplicationLog/Form1.vb#17)]  
  
     형식의 강력한 이름은 프로젝트에 따라 달라집니다.  
  
 강력한 이름을 사용하면 수신기를 `My.Application.Log` 로그 수신기 컬렉션에 추가할 수 있습니다.  
  
#### My.Application.Log에 수신기를 추가하려면  
  
1.  **솔루션 탐색기**에서 app.config를 마우스 오른쪽 단추로 클릭한 다음 **열기**를 선택합니다.  
  
     또는  
  
     app.config 파일이 있을 경우  
  
    1.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  
  
    2.  **새 항목 추가** 대화 상자에서 **응용 프로그램 구성 파일**을 선택합니다.  
  
    3.  **추가**를 클릭합니다.  
  
2.  `name` 특성이 "DefaultSource"인 `<source>` 섹션에서 `<sources>` 섹션에 있는 `<listeners>` 섹션을 찾습니다.  `<sources>` 섹션은 최상위 `<configuration>` 섹션의 `<system.diagnostics>` 섹션에 있습니다.  
  
3.  다음 요소를 `<listeners>` 섹션에 추가합니다.  
  
    ```  
    <add name="SimpleLog" />  
    ```  
  
4.  최상위 `<configuration>` 섹션의 `<system.diagnostics>` 섹션에서 `<sharedListeners>` 섹션을 찾습니다.  
  
5.  다음 요소를 `<sharedListeners>` 섹션에 추가합니다.  
  
    ```  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     `SimpleLogStrongName`의 값을 수신기의 강력한 이름으로 변경합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [방법: 로그 메시지 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [연습: My.Application.Log가 정보를 기록하는 위치 변경](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)