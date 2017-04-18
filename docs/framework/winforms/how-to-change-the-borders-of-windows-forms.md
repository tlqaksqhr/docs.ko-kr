---
title: "방법: Windows Forms의 테두리 변경 | Microsoft Docs"
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
  - "Windows Forms, 테두리 변경"
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms의 테두리 변경
Windows Forms의 모양과 동작을 결정할 때 선택할 수 있는 여러 테두리 스타일이 있습니다.  <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 변경하여 폼의 크기 조정 동작을 제어할 수 있습니다.  또한 <xref:System.Windows.Forms.Form.FormBorderStyle%2A>을 설정하면 캡션 표시줄 표시 방식 및 표시되는 단추에 영향을 줍니다.  자세한 내용은 <xref:System.Windows.Forms.FormBorderStyle>을 참조하세요.  
  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서는 이 작업이 광범위하게 지원됩니다.  
  
 [방법: 디자이너를 사용하여 Windows Forms의 테두리 변경](http://msdn.microsoft.com/library/yettzh3e\(v=vs.110\))을 참조하세요.  
  
### Windows Forms의 테두리 스타일을 프로그래밍 방식으로 설정하려면  
  
-   <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 속성을 원하는 스타일로 설정합니다.  다음 코드 예제에서는`DlgBx1` 폼의 테두리 스타일을 <xref:System.Windows.Forms.FormBorderStyle>로 설정합니다.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     [방법: 디자인 타임에 대화 상자 만들기](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))를 참조하세요.  
  
     또한 선택적 **최소화** 및 **최대화** 단추를 제공하는 폼에 대한 테두리 스타일을 선택한 경우 이러한 단추 중 하나 또는 둘 다를 작동시킬지 여부를 지정할 수 있습니다.  이러한 단추는 사용자 환경을 긴밀히 제어하려는 경우에 유용합니다.  **최소화** 및 **최대화** 단추는 기본적으로 사용되며 **속성** 창을 통해 해당 기능을 조작합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.FormBorderStyle>   
 <xref:System.Windows.Forms.FormBorderStyle>   
 [Windows Forms 시작](../../../docs/framework/winforms/getting-started-with-windows-forms.md)