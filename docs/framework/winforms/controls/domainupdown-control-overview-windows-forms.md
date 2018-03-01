---
title: "DomainUpDown 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5a86dc6c56c3afff8d8a3a4ca2c5d5efa8eac1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="domainupdown-control-overview-windows-forms"></a>DomainUpDown 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤은 한 쌍의 목록에서 위로 또는 아래로 이동 단추 및 텍스트 상자의 조합 합니다. 컨트롤은 표시 하거나 선택 목록에서 텍스트 문자열을 설정 합니다. 위쪽 및 아래쪽 목록 사이 이동 하는 단추를 클릭 하 여, 위쪽 및 아래쪽 화살표 키를 누르거나 또는 목록에 있는 항목과 일치 하는 문자열을 입력 하 여 사용자 문자열을 선택할 수입니다. 이름의 사전순으로 정렬된 된 목록에서 항목을 선택 하는이 컨트롤에 대 한 가능한 사용 됩니다.  
  
> [!NOTE]
>  목록을 정렬 하려면 설정는 <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> 속성을 `true`합니다.  
  
 이 컨트롤의 기능 목록 상자 또는 콤보 상자에 매우 유사 하지만 매우 작은 공간을 차지 합니다.  
  
## <a name="key-properties"></a>키 속성  
 컨트롤의 주요 속성은 <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>, 및 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>합니다. <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성 컨트롤에 텍스트 값을 표시 하는 개체의 목록을 포함 합니다. 경우 <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> 로 설정 된 `false`, 사용자가 하 고 목록에서 값을 일치 하는 텍스트를 자동으로 완성 하는 컨트롤입니다. 경우 <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> 로 설정 된 `true`, 마지막 항목을 스크롤할 첫 번째 항목 목록에서 이동 하 고 그 반대로 이동 합니다. 컨트롤의 주요 메서드는 <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> 및 <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>합니다.  
  
 이 컨트롤에는 텍스트 문자열만 표시 됩니다. 숫자 값을 표시 하는 컨트롤 사용은 <xref:System.Windows.Forms.NumericUpDown> 제어 합니다. 자세한 내용은 참조 [NumericUpDown 컨트롤 개요](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DomainUpDown>  
 [DomainUpDown 컨트롤](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
