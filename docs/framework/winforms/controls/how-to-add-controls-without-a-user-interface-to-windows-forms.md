---
title: '방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 0a3e9ab5a048e085b192ffc0eb796caae1e58efe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가
비시각적 컨트롤 (또는 구성 요소) 응용 프로그램에 기능을 제공합니다. 다른 컨트롤과 달리 구성 요소 사용자에 게 사용자 인터페이스를 제공 하지 않는 및 따라서 Windows Forms 디자이너 화면에 표시 될 필요가 없습니다. 구성 요소는 폼에 추가 되 면 Windows Forms 디자이너 구성 요소를 모두 표시 되는 폼의 아래쪽에 크기를 조정할 수 트레이 표시 합니다. 컨트롤에 구성 요소 트레이에 추가 되 면 구성 요소를 선택한 폼에서 다른 컨트롤 처럼 해당 속성을 설정할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-add-a-component-to-a-windows-form"></a>Windows Form에 구성 요소를 추가 하려면  
  
1.  폼을 엽니다. 자세한 내용은 참조 [하는 방법: Windows Forms 디자이너에 표시](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)합니다.  
  
2.  에 **도구 상자**구성 요소를 클릭 하 고 폼으로 끕니다.  
  
     구성 요소가 구성 요소 트레이에 나타납니다.  
  
 또한 런타임 시 구성 요소는 폼에 추가할 수 있습니다. 이것이 일반적인 시나리오에서 특히 않기 때문에 구성 요소 사용자 인터페이스가 있는 컨트롤과 달리 visual 식입니다. 다음 예제에는 <xref:System.Windows.Forms.Timer> 런타임 시 구성 요소를 추가 합니다. (Visual Studio에는 다른 타이머의 수;이 경우 Windows Forms를 사용 하 여 <xref:System.Windows.Forms.Timer> 구성 요소입니다. Visual Studio에서 다양 한 타이머에 대 한 자세한 내용은 참조 [서버 기반 타이머 소개](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)  
  
> [!CAUTION]
>  구성 요소는 종종 효과적으로 기능 구성 요소에 대해 설정 해야 하는 컨트롤 관련 속성을 가집니다. 경우에 <xref:System.Windows.Forms.Timer> 설정 아래 구성 요소는 `Interval` 속성입니다. 때는 반드시 프로젝트에 속성을 설정 하 고 해당 구성 요소에 필요한 구성 요소를 추가 합니다.  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a>프로그래밍 방식으로 Windows Form에 구성 요소를 추가 하려면  
  
1.  인스턴스를 만들고는 <xref:System.Windows.Forms.Timer> 코드의 클래스.  
  
2.  설정의 `Interval` 속성 타이머 틱 간에 시간을 결정 합니다.  
  
3.  구성 요소에 필요한 기타 속성을 구성 합니다.  
  
     다음 코드와 생성 한 <xref:System.Windows.Forms.Timer> 와 해당 `Interval` 속성 집합입니다.  
  
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
    >  악의적인 UserControl을 참조 로컬 컴퓨터가 네트워크를 통해 보안 위험에 노출 될 수 있습니다. 악의적인 사용자가 실수로 프로젝트에 추가 하는 손상을 일으킬 수 있는 사용자 지정 컨트롤을 만드는 경우 문제가 것만.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)  
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [방법: Windows Forms에 ActiveX 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [방법: Windows Forms 간에 컨트롤 복사](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [Windows Forms에 컨트롤 넣기](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
