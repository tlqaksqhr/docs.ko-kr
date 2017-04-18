---
title: "방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 Tile 보기 사용 | Microsoft Docs"
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
  - "ListView 컨트롤[Windows Forms], Tile 보기"
  - "Tile 보기 기능"
  - "바둑판식 배열, Windows Forms, 컨트롤"
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 Tile 보기 사용
<xref:System.Windows.Forms.ListView> 컨트롤의 Tile 보기 기능을 사용하면 그래픽 정보와 텍스트 정보 간의 시각적 균형을 이룰 수 있습니다.  Tile 보기에서 항목에 대해 표시된 텍스트 정보는 자세히 보기에 대해 정의된 열 정보와 같습니다.  Tile 보기는 <xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 기능이나 삽입 표시 기능과 함께 작동합니다.  
  
 다음과 같은 이미지로 표시되는 Tile 보기에는 32 x 32 아이콘과 여러 줄의 텍스트가 사용됩니다.  
  
 ![ListView 컨트롤의 Tile 보기](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Tile 보기 속성과 메서드를 사용하면 각 항목에 대해 표시할 열 필드를 지정할 수 있으며 Tile 보기 창 내에 있는 모든 항목의 크기와 모양을 일괄적으로 제어할 수 있습니다.  쉽게 구별할 수 있도록 Tile의 텍스트 첫 줄에는 항상 항목 이름이 표시되며 이 이름은 변경할 수 없습니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.ListView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  Tile 보기는 응용 프로그램에서 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> 메서드를 호출할 때 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]에서만 사용할 수 있습니다.  이전 운영 체제에서는 Tile 보기와 관련된 어떤 코드도 적용되지 않으며 <xref:System.Windows.Forms.ListView> 컨트롤은 큰 아이콘 보기로 표시됩니다.  자세한 내용은 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=fullName>를 참조하십시오.  
>   
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너에서 Tile 보기를 설정하려면  
  
1.  폼에서 <xref:System.Windows.Forms.ListView> 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.ListView.View%2A> 속성을 선택한 다음 **Tile**을 선택합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ListView.TileSize%2A>   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ko-kr/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [ListView 컨트롤 개요](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)