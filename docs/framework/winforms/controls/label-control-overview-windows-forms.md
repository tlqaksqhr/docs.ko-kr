---
title: "Label 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "Label"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "이미지[Windows Forms], 레이블에 표시"
  - "Label 컨트롤[Windows Forms], Label 컨트롤 정보"
  - "레이블"
ms.assetid: dcad7f44-11b7-4c55-b0c0-d984ade43d7d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Label 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.Label> 컨트롤은 사용자가 편집할 수 없는 텍스트나 이미지를 표시하는 데 사용됩니다.  이 컨트롤은 폼의 개체를 식별하는 데 사용됩니다. 예를 들어, 특정 컨트롤을 클릭할 경우 수행되는 작업에 대한 설명을 제공하거나 런타임 이벤트 또는 응용 프로그램의 프로세스에 대한 응답 정보를 표시합니다.  예를 들어, 레이블을 사용하여 텍스트 상자, 목록 상자, 콤보 상자 등에 설명 캡션을 추가할 수 있습니다.  또한 런타임에서 이벤트에 응답하여 레이블이 표시하는 텍스트를 변경하는 코드를 작성할 수도 있습니다.  예를 들어 응용 프로그램이 변경 내용을 처리하는 데 몇 분이 걸리는 경우 레이블에 진행 상태 메시지를 표시할 수 있습니다.  
  
## 레이블 컨트롤 사용  
 <xref:System.Windows.Forms.Label> 컨트롤은 포커스를 받을 수 없기 때문에 다른 컨트롤의 선택키를 만드는 데 사용할 수도 있습니다.  Alt 키와 함께 선택키를 누르면 다른 컨트롤을 선택하는 것과 같은 효과를 나타낼 수 있습니다.  자세한 내용은 [Windows Forms 컨트롤에 대한 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) 및 [방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)를 참조하십시오.  
  
 레이블에 표시되는 캡션은 <xref:System.Windows.Forms.Label.Text%2A> 속성에 포함되어 있습니다.  <xref:System.Windows.Forms.Label.TextAlign%2A> 속성을 사용하면 레이블의 텍스트를 정렬할 수 있습니다.  자세한 내용은 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Label>   
 [방법: 내용에 맞게 Windows Forms Label 컨트롤 크기 조정](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)   
 [방법: Windows Forms Label 컨트롤을 사용하여 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)