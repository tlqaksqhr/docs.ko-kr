---
title: TableLayoutPanel 컨트롤에 대한 유용한 정보
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: 40322dc6c5facd4167a4c9ac5c12fdf2a8831b7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526455"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>TableLayoutPanel 컨트롤에 대한 유용한 정보
<xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 Windows Forms에서 사용 하기 전에 신중 하 게 고려해 야 하는 강력한 레이아웃 기능을 제공 합니다.  
  
## <a name="recommendations"></a>권장 사항  
 다음 권장 사항을 사용 하는 데 도움이 됩니다는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 해당 최대한 활용 합니다.  
  
### <a name="targeted-use"></a>사용 대상된  
 사용 된 <xref:System.Windows.Forms.TableLayoutPanel> 제한적으로 제어 합니다. 하지 크기 조정 가능한 레이아웃을 필요로 하는 모든 상황에서 사용 해야 합니다. 다음 목록에는 설명의 사용에서 가장 많이 향상 되는 레이아웃은 <xref:System.Windows.Forms.TableLayoutPanel> 제어:  
  
-   서로 비례적으로 크기를 조정 하는 폼의 여러 부분이 있고 있는 레이아웃입니다.  
  
-   추가 되거나 삭제 된 사용자 지정 가능한 필드가 있는 데이터 항목 형식과 같은 런타임에 동적으로 생성 되거나 수정 될 레이아웃 기본 설정을 기반으로 합니다.  
  
-   전반적인 고정 크기로 유지 해야 하는 레이아웃입니다. 예를 들어 800 x 600 보다 작게 유지 해야 하는 대화 상자를 할 수 있습니다 하지만 지역화 된 문자열을 지원 해야 합니다.  
  
 다음 목록은 레이아웃을 사용 하 여 상당히 유용 하지 않습니다는 <xref:System.Windows.Forms.TableLayoutPanel> 제어:  
  
-   간단한 데이터 입력 폼 단일 열과 레이블 및 텍스트 입력 영역으로 이루어진 단일 열입니다.  
  
-   큰 단일 폼 크기를 조정 하면 사용 가능한 모든 공간을 채워야 하는 영역을 표시 합니다. 이 예는 단일 표시 하는 폼 <xref:System.Windows.Forms.PropertyGrid> 제어 합니다. 이 경우 폼의 크기를 조정할 때 확장 해야만 수행 되기 때문에 앵커를 사용 합니다.  
  
 선택 신중 하 게 제어 하에 있이 필요는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다. 앵커를 사용 하 여 30% 증가 하려고 텍스트 공간이 있는 경우 사용 하 여 고려는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성에만 해당 합니다. 레이아웃에 필요한 공간을 예측할 수 경우 활용 <xref:System.Windows.Forms.Control.Dock%2A> 및 <xref:System.Windows.Forms.Control.Anchor%2A> 남아 있는 공간에 대 한 세부 정보를 예측 하는 것 보다 쉽습니다 및 <xref:System.Windows.Forms.Control.AutoSize%2A> 동작 합니다.  
  
 일반적으로 사용 하 여 레이아웃을 디자인 하는 경우는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 디자인을 가능한 한 단순하게 유지 합니다.  
  
### <a name="use-the-document-outline-window"></a>문서 개요 창을 사용 하 여  
 문서 개요 창 컨트롤의 z 순서와 부모-자식 관계를 조작 하는 데 사용할 수 있는 레이아웃의 트리 보기를 제공 합니다. **보기 메뉴**선택, **다른 창**을 선택한 후 **문서 개요**합니다.  
  
### <a name="avoid-nesting"></a>중첩을 하지 마십시오  
 다른 중첩 하지 마십시오 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 내에 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다. 중첩 된 레이아웃을 디버깅 하는 것은 어려울 수 있습니다.  
  
### <a name="avoid-visual-inheritance"></a>시각적 상속을 하지 마십시오.  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 Windows Forms 디자이너에서 시각적 상속을 지원 하지 않습니다. A <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 파생된 클래스에서 "잠겨 있음" 디자인 타임에 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
