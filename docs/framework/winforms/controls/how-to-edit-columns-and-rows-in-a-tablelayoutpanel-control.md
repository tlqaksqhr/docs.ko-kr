---
title: "방법: TableLayoutPanel 컨트롤에서 열과 행 편집 | Microsoft Docs"
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
  - "net.ComponentModel.StyleCollectionEditor"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "열[Windows Forms], 편집"
  - "행[Windows Forms], 편집"
  - "TableLayoutPanel 컨트롤[Windows Forms], 편집"
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: TableLayoutPanel 컨트롤에서 열과 행 편집
**열 및 행 스타일** 대화 상자라는 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 컬렉션 편집기를 사용하여 컨트롤의 행과 열을 편집할 수 있습니다.  
  
> [!NOTE]
>  컨트롤에서 여러 행이나 열을 확장하려면 `RowSpan` 및 `ColumnSpan` 속성을 해당 컨트롤에 설정합니다.  자세한 내용은 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조하십시오.  
>   
>  셀 내에서 컨트롤을 맞추거나 확장하려면 컨트롤의 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 사용합니다.  자세한 내용은 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)을 참조하십시오.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 행과 열을 편집하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭하고 **행 및 열 편집**을 선택하여 **열 및 행 스타일** 대화 상자를 엽니다.  또한 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **행 및 열 편집**을 선택할 수도 있습니다.  
  
3.  열을 추가 또는 제거하려면 **멤버 형식** 드롭다운 목록 상자에서 **열**을 선택합니다.  
  
4.  행을 추가 또는 제거하려면 **멤버 형식** 드롭다운 목록 상자에서 **행**을 선택합니다.  
  
5.  **추가** 단추를 클릭하여 행 또는 열을 **멤버** 목록의 끝에 추가합니다.  
  
6.  **삽입** 단추를 클릭하여 행 또는 열을 목록에서 현재 선택된 항목 앞에 추가합니다.  
  
7.  행 또는 열을 추가하는 경우 새 행 또는 열의 **크기 형식**을 선택합니다.  자세한 내용은 <xref:System.Windows.Forms.SizeType>을 참조하십시오.  
  
8.  행 또는 열을 제거하려면 **제거** 단추를 클릭하여 **멤버** 목록에서 현재 선택된 항목을 삭제합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.SizeType>   
 [TableLayoutPanel 컨트롤](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)