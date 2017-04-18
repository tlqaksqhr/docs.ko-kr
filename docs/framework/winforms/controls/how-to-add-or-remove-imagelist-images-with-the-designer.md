---
title: "방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거 | Microsoft Docs"
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
  - "ImageList 구성 요소[Windows Forms], 이미지 추가"
  - "ImageList 구성 요소[Windows Forms], 이미지 제거"
  - "이미지[Windows Forms], ImageList 구성 요소에 추가"
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 디자이너를 사용하여 ImageList 이미지 추가 또는 제거
몇 가지 방법으로 <xref:System.Windows.Forms.ImageList> 구성 요소에 이미지를 추가할 수 있습니다.  <xref:System.Windows.Forms.ImageList>에 연결된 스마트 태그를 사용하여 매우 빠르게 이미지를 추가할 수 있으며, <xref:System.Windows.Forms.ImageList>에서 다른 몇 가지 속성을 설정하는 경우에는 속성 창을 사용하여 보다 손쉽게 이미지를 추가할 수 있습니다.  코드를 사용하여 이미지를 추가할 수도 있습니다.  코드를 사용하여 이미지를 추가하는 방법에 대한 자세한 내용은 [방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 참조하십시오.  컨트롤에 연결하기 전에 <xref:System.Windows.Forms.ImageList> 구성 요소를 이미지로 채우는 방법이 일반적이긴 하지만 반드시 그렇게 할 필요는 없습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 속성 창을 사용하여 이미지를 추가하거나 제거하려면  
  
1.  <xref:System.Windows.Forms.ImageList> 구성 요소를 선택하거나 폼에 이 구성 요소를 추가합니다.  
  
2.  속성 창에서 <xref:System.Windows.Forms.ImageList.Images%2A> 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭합니다.  
  
3.  **이미지 컬렉션 편집기**에서 **추가** 또는 **제거**를 클릭하여 목록에서 이미지를 추가하거나 제거합니다.  
  
### 스마트 태그를 사용하여 이미지를 추가하거나 제거하려면  
  
1.  <xref:System.Windows.Forms.ImageList> 구성 요소를 선택하거나 폼에 이 구성 요소를 추가합니다.  
  
2.  스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭합니다.  
  
3.  **ImageList 작업** 대화 상자에서 **이미지 선택**을 선택합니다.  
  
4.  **이미지 컬렉션 편집기**에서 **추가** 또는 **제거**를 클릭하여 목록에서 이미지를 추가하거나 제거합니다.  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)   
 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)