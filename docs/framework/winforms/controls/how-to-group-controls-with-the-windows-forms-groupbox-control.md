---
title: "방법: Windows Forms GroupBox 컨트롤을 사용하여 컨트롤 그룹화 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤[Windows Forms], 그룹화"
  - "GroupBox 컨트롤[Windows Forms], 컨트롤 그룹화"
  - "Windows Forms 컨트롤, 그룹화"
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Windows Forms GroupBox 컨트롤을 사용하여 컨트롤 그룹화
Windows Forms <xref:System.Windows.Forms.GroupBox> 컨트롤은 다른 컨트롤을 그룹화하는 데 사용됩니다.  컨트롤을 그룹화하는 데에는 다음과 같은 세 가지 이유가 있습니다.  
  
-   관련된 폼 요소를 시각적으로 그룹화하여 명확한 사용자 인터페이스를 제공할 수 있습니다.  
  
-   프로그래밍 방식으로 그룹화할 수 있습니다\(예: 라디오 단추\).  
  
-   디자인 타임에서 여러 컨트롤을 한 단위로 이동할 수 있습니다.  
  
### 컨트롤 그룹을 만들려면  
  
1.  폼에 <xref:System.Windows.Forms.GroupBox> 컨트롤을 그립니다.  
  
2.  다른 컨트롤을 그룹 상자에 추가한 다음 해당 그룹 상자 안에서 각 컨트롤을 그립니다.  
  
     기존 컨트롤을 그룹 상자에 포함하려면 모든 컨트롤을 선택하여 클립보드에 잘라 낸 다음 <xref:System.Windows.Forms.GroupBox> 컨트롤을 선택하여 그룹 상자에 붙여넣습니다.  그룹 상자에 직접 끌어 올 수도 있습니다  
  
3.  그룹 상자의 <xref:System.Windows.Forms.GroupBox.Text%2A> 속성에 적절한 캡션을 설정합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.GroupBox>   
 [GroupBox 컨트롤](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)