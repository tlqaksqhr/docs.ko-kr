---
title: DomainUpDown 컨트롤(Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: c23f374f1ec9cab6e43b12d32b97c40533ac36cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527328"
---
# <a name="domainupdown-control-windows-forms"></a>DomainUpDown 컨트롤(Windows Forms)
Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤 쌍의 단추와 텍스트 상자의 조합 용 모양 목록에서 위로 또는 아래로 이동 합니다. 컨트롤은 표시 하거나 선택 목록에서 텍스트 문자열을 설정 합니다. 위쪽 및 아래쪽 목록 사이 이동 하는 단추를 클릭 하 여, 위쪽 및 아래쪽 화살표 키를 누르거나 또는 목록에 있는 항목과 일치 하는 문자열을 입력 하 여 사용자 문자열을 선택할 수입니다. 이름의 사전순으로 정렬된 된 목록에서 항목을 선택 하는이 컨트롤에 대 한 가능한 사용 됩니다. (설정 목록을 정렬 하는 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 속성을 `true`.) 이 컨트롤의 기능 목록 상자 또는 콤보 상자에 매우 유사 하지만 매우 작은 공간을 차지 합니다.  
  
 컨트롤의 주요 속성은 <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, 및 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>합니다. <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성 컨트롤에 텍스트 값을 표시 하는 개체의 목록을 포함 합니다. 경우 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 로 설정 된 `false`, 사용자가 하 고 목록에서 값을 일치 하는 텍스트를 자동으로 완성 하는 컨트롤입니다. 경우 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 로 설정 된 `true`, 마지막 항목을 스크롤할 첫 번째 항목 목록에서 이동 하 고 그 반대로 이동 합니다. 컨트롤의 주요 메서드는 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 및 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>합니다.  
  
 이 컨트롤에는 텍스트 문자열만 표시 됩니다. 숫자 값을 표시 하는 컨트롤 사용은 <xref:System.Windows.Forms.NumericUpDown> 제어 합니다. 자세한 내용은 참조 [NumericUpDown 컨트롤](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md) 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [DomainUpDown 컨트롤 개요](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)  
 일반적인 개념을 소개는 <xref:System.Windows.Forms.DomainUpDown> 컨트롤 사용자가 탐색 하 고 텍스트 문자열의 목록에서 선택할 수 있습니다.  
  
 [방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가](../../../../docs/framework/winforms/controls/how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 텍스트 문자열을 지정 하는 방법에 설명 된 <xref:System.Windows.Forms.DomainUpDown> 표시 해야 합니다.  
  
 [방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거](../../../../docs/framework/winforms/controls/how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 항목을 삭제 하는 방법에 설명 된 <xref:System.Windows.Forms.DomainUpDown> 코드에서 컨트롤입니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.DomainUpDown>  
 이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 이 클래스를 설명 하 고 모든 해당 멤버에 대 한 링크가...  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Forms에서 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.
