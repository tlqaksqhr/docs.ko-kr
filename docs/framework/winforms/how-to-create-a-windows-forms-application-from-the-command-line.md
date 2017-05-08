---
title: "방법: 명령줄에서 Windows Forms 응용 프로그램 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, 명령줄에서 응용 프로그램 개발"
  - "Windows Forms, 기본 폼 만들기"
  - "Windows Forms, 시작"
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 명령줄에서 Windows Forms 응용 프로그램 만들기
다음 절차에서는 명령줄에서 Windows Forms 응용 프로그램을 만들고 실행하기 위해 완료해야 하는 기본 단계를 설명합니다.  Visual Studio에서는 이러한 절차가 광범위하게 지원됩니다.  [연습: 간단한 Windows Form 만들기](http://msdn.microsoft.com/library/z9w2f38k\(v=vs.110\))를 참조하세요.  
  
## 프로시저  
  
#### 폼을 만들려면  
  
1.  빈 코드 파일에서 다음 import 또는 using 문을 입력합니다.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2.  Form 클래스에서 상속되는 `Form1`이라는 클래스를 선언합니다.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3.  `Form1`에 대한 기본 생성자를 만듭니다.  
  
     이후 절차에서 생성자에 더 많은 코드를 추가합니다.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4.  클래스에 `Main` 메서드를 추가합니다.  
  
    1.  `Main` 메서드에 <xref:System.STAThreadAttribute>를 적용하여 Windows Forms 응용 프로그램을 단일 스레드 아파트로 지정합니다.  
  
    2.  <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>를 호출하여 응용 프로그램에 Windows XP 모양을 제공합니다.  
  
    3.  폼 인스턴스를 만들고 실행합니다.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### 응용 프로그램을 컴파일하고 실행하려면  
  
1.  .NET Framework 명령 프롬프트에서 `Form1` 클래스를 만든 디렉터리로 이동합니다.  
  
2.  폼을 컴파일합니다.  
  
    -   C\#을 사용하는 경우 `csc form1.cs`를 입력합니다.  
  
         `또는`  
  
    -   Visual Basic을 사용하는 경우 `vbc form1.vb /r:system.dll,system.drawing.dll,system.windows.forms.dll`을 입력합니다.  
  
3.  명령 프롬프트에서 `Form1.exe`를 입력합니다.  
  
## 컨트롤 추가 및 이벤트 처리  
 이전 절차의 단계에서는 컴파일 및 실행되는 기본 Windows Form을 만드는 방법만 보여 주었습니다.  다음 절차에서는 컨트롤을 만들고 폼에 추가한 다음 컨트롤에 대한 이벤트를 처리하는 방법을 보여 줍니다.  Windows Forms에 추가할 수 있는 컨트롤에 대한 자세한 내용은 [Windows Forms 컨트롤](../../../docs/framework/winforms/controls/index.md)을 참조하세요.  
  
 Windows Forms 응용 프로그램을 만드는 방법을 이해하는 것은 물론 이벤트 기반 프로그래밍 및 사용자 입력을 처리하는 방법도 이해해야 합니다.  자세한 내용은 [Windows Forms에서 이벤트 처리기 만들기](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md) 및 [사용자 입력 처리](../../../docs/framework/winforms/controls/handling-user-input.md)를 참조하세요.  
  
#### 단추 컨트롤을 선언하고 해당 click 이벤트를 처리하려면  
  
1.  `button1`이라는 단추 컨트롤을 선언합니다.  
  
2.  생성자에서 단추를 만들고 해당 <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> 및 <xref:System.Windows.Forms.Control.Text%2A> 속성을 설정합니다.  
  
3.  폼에 단추를 추가합니다.  
  
     다음 코드 예제에서는 단추 컨트롤을 선언하는 방법을 보여 줍니다.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4.  단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리할 메서드를 만듭니다.  
  
5.  click 이벤트 처리기에서 "Hello World" 메시지와 함께 <xref:System.Windows.Forms.MessageBox>를 표시합니다.  
  
     다음 코드 예제에서는 단추 컨트롤의 click 이벤트를 처리하는 방법을 보여 줍니다.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6.  만든 메서드에 <xref:System.Windows.Forms.Control.Click> 이벤트를 연결합니다.  
  
     다음 코드 예제에서는 이벤트를 메서드에 연결하는 방법을 보여 줍니다.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7.  이전 절차에서 설명한 대로 응용 프로그램을 컴파일 및 실행합니다.  
  
## 예제  
 다음 코드 예제는 이전 절차의 전체 예제입니다.  
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## 코드 컴파일  
  
-   코드를 컴파일하려면 응용 프로그램을 컴파일 및 실행하는 방법을 설명하는 이전 절차의 지침을 따릅니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Form>   
 <xref:System.Windows.Forms.Control>   
 [Windows Forms의 모양 변경](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)   
 [Windows Forms 응용 프로그램 강화](../../../docs/framework/winforms/advanced/index.md)   
 [Windows Forms 시작](../../../docs/framework/winforms/getting-started-with-windows-forms.md)