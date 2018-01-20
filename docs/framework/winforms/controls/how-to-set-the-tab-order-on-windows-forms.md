---
title: "방법: Windows Forms에서 탭 순서 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de52a4d7784eb4508d5cf5026b394b7b63ecc56e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>방법: Windows Forms에서 탭 순서 설정
탭 순서는 사용자가 이동 포커스가 한 컨트롤에서 다른 TAB 키를 눌러 순서는 않습니다. 각 폼에는 자체 탭 순서입니다. 기본적으로 탭 순서는 컨트롤을 만든 순서와 같습니다. 탭 순서 번호는 0부터 시작 합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-set-the-tab-order-of-a-control"></a>컨트롤의 탭 순서 설정  
  
1.  에 **보기** 메뉴를 클릭 하 여 **탭 순서**합니다.  
  
     양식에서 탭 순서 선택 모드를 활성화합니다. 숫자 (나타내는 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성) 각 컨트롤의 왼쪽 위 모서리에 나타납니다.  
  
2.  원하는 탭 순서를 설정 하는 순차적으로 컨트롤을 클릭 합니다.  
  
    > [!NOTE]
    >  탭 순서는 컨트롤의 위치는 0 보다 크거나 값으로 설정할 수 있습니다. 중복이 발생 하는 경우 두 컨트롤의 z 순서 계산 되 고 맨 위에 있는 컨트롤이 탭 처음으로 구성 됩니다. (Z-순서는 폼의 z 축 [깊이]와 함께 폼에 컨트롤의 시각적 계층 않습니다. Z 좌표는 컨트롤 결정 앞뒤 합니다.) Z-순서에 대 한 자세한 내용은 참조 하십시오. [Windows Forms에서 개체 계층화](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md)합니다.  
  
3.  완료 되 면 클릭 **탭 순서** 에 **보기** 메뉴 다시 탭 순서 모드를 종료 합니다.  
  
    > [!NOTE]
    >  사용 안 함 및 보이지 않는 컨트롤 뿐 아니라 포커스를 받을 수 없는 컨트롤 하지 않은 한 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성 및은 탭 순서에 포함 되지 합니다. TAB 키를 누를 때 이러한 컨트롤은 건너뜁니다.  
  
 또는 탭 순서를 사용 하 여 속성 창에서 설정할 수는 <xref:System.Windows.Forms.Control.TabIndex%2A> 속성입니다. <xref:System.Windows.Forms.Control.TabIndex%2A> 속성 컨트롤의 탭 순서에 배치 되는 위치를 결정 합니다. 기본적으로 그린 첫 번째 컨트롤에는 <xref:System.Windows.Forms.Control.TabIndex%2A> 값 0을 두 번째는는 <xref:System.Windows.Forms.Control.TabIndex%2A> 1, 및 등입니다.  
  
 또한 기본적으로 <xref:System.Windows.Forms.GroupBox> 컨트롤에 고유한 <xref:System.Windows.Forms.Control.TabIndex%2A> 값은 정수입니다. A <xref:System.Windows.Forms.GroupBox> 런타임 시 컨트롤 자체 포커스를 가질 수 없습니다. 따라서 각 컨트롤 내에서 한 <xref:System.Windows.Forms.GroupBox> 는 고유한 10 진수 <xref:System.Windows.Forms.Control.TabIndex%2A> .0 부터는 값입니다. 기본적으로 <xref:System.Windows.Forms.Control.TabIndex%2A> 의 <xref:System.Windows.Forms.GroupBox> 컨트롤 증가, 내에 있는 컨트롤을 적절 하 게 증가 합니다. 변경한 경우에 <xref:System.Windows.Forms.Control.TabIndex%2A> 5-6의 값은 <xref:System.Windows.Forms.Control.TabIndex%2A> 해당 그룹의 첫 번째 컨트롤의 값이 자동으로 6.0 및 등을 변경 합니다.  
  
 마지막으로, 특정 컨트롤을 다로 폼의 탭 순서에서 건너뛸 수 있습니다. 일반적으로 TAB 키를 누르면 연속적으로 실행된 시간 선택에서 탭 순서에서 각 컨트롤입니다. 전원을 켜는 방식으로 <xref:System.Windows.Forms.Control.TabStop%2A> 속성 폼의 탭 순서에서를 통해 전달 되어야 하는 컨트롤을 만들 수 있습니다.  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a>탭 순서에서 컨트롤을 제거 하려면  
  
1.  컨트롤의 <xref:System.Windows.Forms.Control.TabStop%2A> 속성을 `false` 속성 창에서.  
  
     A 컨트롤 <xref:System.Windows.Forms.Control.TabStop%2A> 속성이 설정 되어 `false` TAB 키로 컨트롤을 순환 하는 경우 컨트롤을 건너 하는 경우에 여전히 탭 순서에서 그 위치를 유지 합니다.  
  
    > [!NOTE]
    >  라디오 단추 그룹 실행 시 단일 탭을 있습니다. 선택한 단추 (사용 하 여 단추, 즉 해당 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성이로 설정 `true`)가 해당 <xref:System.Windows.Forms.Control.TabStop%2A> 속성으로 자동 설정 `true`다른 단추를 포함 하는 반면, 해당 <xref:System.Windows.Forms.Control.TabStop%2A> 속성이로 설정 `false`합니다. 그룹화에 대 한 자세한 내용은 <xref:System.Windows.Forms.RadioButton> 컨트롤 참조 [집합으로 함수에 Windows Forms RadioButton 컨트롤 그룹화](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)  
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
