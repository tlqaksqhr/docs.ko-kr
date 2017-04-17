---
title: "방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NonVisualSelection"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms], 보이지 않는 상태"
  - "보이지 않는 컨트롤"
  - "보이지 않는 컨트롤"
  - "Windows Forms 컨트롤, 폼에 추가"
  - "Windows Forms 컨트롤, 보이지 않는 상태"
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가
비시각적 컨트롤이나 구성 요소는 응용 프로그램에 기능성을 제공합니다.  다른 컨트롤과 달리 구성 요소는 사용자 인터페이스를 제공하지 않으므로 Windows Forms 디자이너 화면에 표시될 필요가 없습니다.  폼에 구성 요소를 추가하면 Windows Forms 디자이너는 모든 구성 요소가 표시된 폼 아래에 크기를 조정할 수 있는 트레이를 표시합니다.  구성 요소 트레이에 컨트롤을 추가하면 폼에 있는 다른 컨트롤과 마찬가지로 구성 요소를 선택하고 속성을 설정할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### Windows Form에 구성 요소를 추가하려면  
  
1.  폼을 엽니다.  자세한 내용은 [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/ko-kr/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)를 참조하십시오.  
  
2.  **도구 상자**에서 구성 요소를 클릭한 다음 폼으로 끌어 옵니다.  
  
     구성 요소 트레이에 구성 요소가 나타납니다.  
  
 또한 런타임에 구성 요소를 추가할 수도 있습니다.  특히 구성 요소는 사용자 인터페이스를 가지고 있는 컨트롤과 달리 시각적인 식을 가지고 있지 않으므로 런타임에 추가하는 것이 일반적입니다.  아래의 예제에서는 <xref:System.Windows.Forms.Timer> 구성 요소가 런타임에 추가됩니다.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에는 다양한 타이머가 포함되어 있지만, 이 예제에서는 Windows Forms <xref:System.Windows.Forms.Timer> 구성 요소를 사용합니다.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]의 다양한 타이머에 대한 자세한 내용은 [Introduction to Server\-Based Timers](http://msdn.microsoft.com/ko-kr/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)를 참조하십시오.  
  
> [!CAUTION]
>  구성 요소에는 구성 요소의 효과적인 작동을 위해 설정해야 하는 컨트롤별 속성이 있는 경우가 많습니다.  아래 <xref:System.Windows.Forms.Timer> 구성 요소의 경우에는 `Interval` 속성을 설정합니다.  프로젝트에 구성 요소를 추가할 때는 반드시 해당 구성 요소에 필요한 속성을 설정해야 합니다.  
  
#### 프로그래밍 방식으로 Windows Form에 구성 요소를 추가하려면  
  
1.  <xref:System.Windows.Forms.Timer> 클래스의 인스턴스를 코드로 만듭니다.  
  
2.  `Interval` 속성을 설정하여 타이머 눈금 사이의 간격을 결정합니다.  
  
3.  구성 요소에 필요한 기타 속성을 구성합니다.  
  
     다음 코드에서는 `Interval` 속성이 설정된 <xref:System.Windows.Forms.Timer>를 만드는 방법을 보여 줍니다.  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  악의적인 UserControl을 참조하면 네트워크를 통해 로컬 컴퓨터가 보안 위험에 노출될 수 있습니다.  악의를 가진 사람이 유해한 사용자 지정 컨트롤을 만들고 개발자가 실수로 프로젝트에 이 컨트롤을 추가하는 경우에만 이러한 문제가 발생합니다.  
  
## 참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [방법: Windows Forms에 ActiveX 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)   
 [방법: Windows Forms 간에 컨트롤 복사](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)   
 [Windows Forms에 컨트롤 넣기](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)   
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)