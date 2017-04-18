---
title: "ImageList 구성 요소 개요(Windows Forms) | Microsoft Docs"
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
  - "ImageList"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컬렉션 컨트롤, 이미지"
  - "아이콘 목록 컨트롤"
  - "ImageList 구성 요소[Windows Forms], ImageList 구성 요소 정보"
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# ImageList 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ImageList> 구성 요소는 컨트롤에 의해 표시될 수 있는 이미지를 저장하는 데 사용됩니다.  이미지 목록을 통해 일관된 단일 이미지 카탈로그에 대한 코드를 작성할 수 있습니다.  예를 들어 단추의 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> 또는 <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> 속성을 변경하여 <xref:System.Windows.Forms.Button> 컨트롤에 의해 표시되는 이미지를 회전할 수 있습니다.  동일한 이미지 목록을 여러 컨트롤에 연결할 수도 있습니다.  예를 들어 <xref:System.Windows.Forms.ListView> 컨트롤과 <xref:System.Windows.Forms.TreeView> 컨트롤 둘 다를 사용하여 동일한 파일 목록을 표시하는 경우 이미지 목록에서 파일 아이콘을 변경하면 두 보기에 모두 새 아이콘이 나타납니다.  
  
## 컨트롤과 함께 ImageList 사용  
 `ImageList` 속성 또는 <xref:System.Windows.Forms.ListView> 컨트롤의 경우 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 및 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 속성이 있는 모든 컨트롤과 함께 이미지 목록을 사용할 수 있습니다.  이미지 목록에 연결할 수 있는 컨트롤에는 <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton> 및 <xref:System.Windows.Forms.Label> 컨트롤이 포함됩니다.  이미지 목록을 컨트롤에 연결하려면 컨트롤의 `ImageList` 속성을 <xref:System.Windows.Forms.ImageList> 구성 요소의 이름으로 설정합니다.  
  
## 키 속성  
 <xref:System.Windows.Forms.ImageList> 구성 요소의 키 속성은 연결된 컨트롤에서 사용할 그림을 포함하는 <xref:System.Windows.Forms.ImageList.Images%2A>입니다.  인덱스 값이나 해당 키를 통해 각 개별 이미지에 액세스할 수 있습니다.  <xref:System.Windows.Forms.ImageList.ColorDepth%2A> 속성은 이미지 렌더링에 사용되는 색 수를 결정합니다.  이미지는 모두 <xref:System.Windows.Forms.ImageList.ImageSize%2A> 속성에 설정된 동일한 크기로 표시됩니다.  더 큰 이미지는 적절하게 크기가 조정됩니다.  
  
 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]를 사용 중인 경우 응용 프로그램에서 사용할 수 있는 표준 이미지의 대규모 라이브러리에 액세스할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ImageList>   
 [방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)