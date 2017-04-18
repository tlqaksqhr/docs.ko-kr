---
title: "방법: Windows Forms 응용 프로그램에서 글꼴 구성표 변경에 응답 | Microsoft Docs"
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
  - "Windows Forms, 글꼴 구성표 변경"
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Windows Forms 응용 프로그램에서 글꼴 구성표 변경에 응답
사용자는 Windows 운영 체제에서 시스템 차원의 글꼴 설정을 변경하여 기본 글꼴을 보다 크게 표시하거나 작게 표시할 수 있습니다.  이러한 글꼴 설정을 변경하는 작업은 시각 장애가 있어서 화면 상에 나타나는 텍스트를 읽으려면 보다 큰 형식의 글꼴이 필요한 사용자에게 매우 중요합니다.  Windows Forms 응용 프로그램을 조정하여 글꼴 구성표가 변경될 때마다 폼과 폼에 포함된 모든 텍스트의 크기를 증가시키거나 감소시켜 이러한 변경에 응답하도록 할 수 있습니다.  폼에서 글꼴 크기 변경을 동적으로 수용하도록 하려면 폼에 코드를 추가합니다.  
  
 일반적으로 Windows Forms에 사용되는 기본 글꼴은 `GetStockObject(DEFAULT_GUI_FONT)`에 대한 <xref:Microsoft.Win32> 네임스페이스 호출에서 반환하는 글꼴입니다.  이 호출에서 반환하는 글꼴은 화면 해상도를 변경할 때만 변경됩니다.  다음 절차에서 볼 수 있는 것처럼 글꼴 크기 변경에 응답하기 위해서는 코드에서 기본 글꼴을 <xref:System.Drawing.SystemFonts.IconTitleFont%2A>로 변경해야 합니다.  
  
### 바탕 화면 글꼴을 사용하여 글꼴 구성표 변경에 응답하려면  
  
1.  폼을 만든 다음 원하는 컨트롤을 추가합니다.  자세한 내용은 [방법: 명령줄에서 Windows Forms 응용 프로그램 만들기](../../../docs/framework/winforms/how-to-create-a-windows-forms-application-from-the-command-line.md) 및 [Windows Forms에 사용할 수 있는 컨트롤](../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)을 참조하십시오.  
  
2.  <xref:Microsoft.Win32> 네임스페이스에 대한 참조를 코드에 추가합니다.  
  
     [!code-csharp[WinFormsAutoScaling#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 후크하고 폼에서 사용 중인 기본 글꼴을 변경합니다.  
  
     [!code-csharp[WinFormsAutoScaling#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <xref:Microsoft.Win32.UserPreferenceCategory> 범주가 변경될 때 폼의 크기를 자동으로 조정하는 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 이벤트의 처리기를 구현합니다.  
  
     [!code-csharp[WinFormsAutoScaling#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  마지막으로 <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> 이벤트 처리기를 분리하는 <xref:System.Windows.Forms.Form.FormClosing> 이벤트의 처리기를 구현합니다.  
  
> [!IMPORTANT]
>  이 코드를 포함하지 않으면 응용 프로그램에 메모리 누수가 발생합니다.  
  
 [!code-csharp[WinFormsAutoScaling#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
 [!code-vb[WinFormsAutoScaling#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
1.  코드를 컴파일하고 실행합니다.  
  
### Windows XP에서 글꼴 구성표를 수동으로 변경하려면  
  
1.  Windows Forms 응용 프로그램 실행 중에 Windows 바탕 화면을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **속성**을 선택합니다.  
  
2.  **디스플레이 속성** 대화 상자에서 **모양** 탭을 클릭합니다.  
  
3.  **글꼴 크기** 드롭다운 목록 상자에서 새 글꼴 크기를 선택합니다.  
  
     폼에서 바탕 화면 글꼴 구성표에 대한 런타임 변경에 응답하는 것을 볼 수 있습니다.  사용자가 **보통**, **큰 글꼴** 및 **아주 큰 글꼴** 등으로 글꼴을 변경하면 폼에서도 글꼴이 변경되고 크기가 올바르게 조정됩니다.  
  
## 예제  
 [!code-csharp[WinFormsAutoScaling#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 이 코드 예제의 생성자는 Visual Studio에서 새 Windows Forms 프로젝트를 만들 때 정의되는 `InitializeComponent`에 대한 호출을 포함합니다.  명령줄에서 응용 프로그램을 작성 중인 경우에는 이 코드 줄을 제거합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>   
 [Windows Forms의 자동 배율 조정](../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md)