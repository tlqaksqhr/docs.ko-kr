---
title: "TableLayoutPanel 컨트롤에 대한 유용한 정보 | Microsoft Docs"
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
  - "자동 크기 조정"
  - "AutoSize 속성, TableLayoutPanel 컨트롤"
  - "유용한 정보, TableLayoutPanel 컨트롤"
  - "컨트롤[Windows Forms], 크기 조정"
  - "폼, 유용한 정보"
  - "레이아웃[Windows Forms]"
  - "레이아웃[Windows Forms], 유용한 정보"
  - "레이아웃[Windows Forms], AutoSize"
  - "크기 조정, 자동"
  - "TableLayoutPanel 컨트롤[Windows Forms], 유용한 정보"
  - "TableLayoutPanel 컨트롤[Windows Forms], AutoSize 동작"
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# TableLayoutPanel 컨트롤에 대한 유용한 정보
<xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 통해 Windows Forms에서 사용하기 전에 신중하게 고려해야 할 강력한 레이아웃 기능을 사용할 수 있습니다.  
  
## 권장 사항  
 다음 권장 사항은 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 최대한 효율적으로 사용하는 데 도움이 됩니다.  
  
### 사용 대상  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 꼭 필요한 경우에만 사용해야 하며  레이아웃의 크기를 조정해야 하는 아무 상황에서나 사용하면 안 됩니다.  다음 목록에서는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 큰 효과를 볼 수 있는 레이아웃에 대해 설명합니다.  
  
-   여러 부분으로 구성되어 이러한 부분이 비례적으로 크기가 조정되는 폼의 레이아웃  
  
-   기본 설정에 따라 추가되거나 삭제된 사용자 지정 가능한 필드가 포함된 데이터 입력 폼과 같이 런타임에 동적으로 수정되거나 생성될 레이아웃  
  
-   전체 고정 크기로 유지되어야 하는 레이아웃.  예를 들어, 대화 상자를 800 x 600보다 작게 유지해야 하지만 지역화된 문자열을 지원해야 하는 경우를 들 수 있습니다.  
  
 다음 목록에서는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용해도 큰 효과를 보지 못하는 레이아웃에 대해 설명합니다.  
  
-   단일 레이블 열 및 단일 텍스트 입력 영역 열이 포함된 간단한 데이터 입력 폼  
  
-   크기를 조정하면 사용 가능한 모든 공간을 채워야 하는 큰 단일 표시 영역이 포함된 폼.  단일 <xref:System.Windows.Forms.PropertyGrid> 컨트롤을 표시하는 폼을 예로 들 수 있습니다.  이 경우 폼의 크기를 조정할 때 다른 영역은 확장되지 않아야 하므로 앵커를 사용합니다.  
  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 필요한 컨트롤을 주의해서 선택합니다.  앵커를 사용하여 30%씩 늘릴 수 있는 텍스트 공간이 있는 경우에는 <xref:System.Windows.Forms.Control.Anchor%2A> 속성만 사용하는 것이 좋습니다.  레이아웃에 필요한 공간을 추정할 수 있는 경우 <xref:System.Windows.Forms.Control.Dock%2A> 및 <xref:System.Windows.Forms.Control.Anchor%2A>를 사용하는 것이 나머지 공간과 <xref:System.Windows.Forms.Control.AutoSize%2A> 동작을 세부적으로 추정하는 것보다 쉽습니다.  
  
 일반적으로 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 사용하여 레이아웃을 디자인할 때는 디자인을 가능한 한 단순하게 해야 합니다.  
  
### 문서 개요 창 사용  
 문서 개요 창에는 레이아웃의 트리 뷰가 표시되므로 이를 사용하여 컨트롤의 z 순서와 부모\/자식 관계를 조작할 수 있습니다.  **보기** 메뉴에서 **다른 창**, **문서 개요**를 차례로 선택합니다.  
  
### 중첩 사용하지 않기  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 내에 다른 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 중첩하지 마십시오.  중첩된 레이아웃은 디버깅하기가 어렵습니다.  
  
### 시각적 상속 사용하지 않기  
 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 Windows Forms 디자이너에서 시각적 상속을 지원하지 않습니다.  파생 클래스의 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤은 디자인 타임에 "잠금" 상태로 나타납니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 <xref:System.Windows.Forms.FlowLayoutPanel>