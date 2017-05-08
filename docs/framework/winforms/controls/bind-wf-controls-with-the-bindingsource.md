---
title: "방법: 디자이너를 사용하여 Windows Forms 컨트롤에 BindingSource 구성 요소 바인딩 | Microsoft Docs"
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
  - "BindingSource 구성 요소[Windows Forms], 컨트롤 바인딩"
  - "컨트롤[Windows Forms], 바인딩"
  - "데이터 바인딩, BindingSource 구성 요소"
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: 디자이너를 사용하여 Windows Forms 컨트롤에 BindingSource 구성 요소 바인딩
폼에 컨트롤을 추가한 다음 응용 프로그램에 사용할 사용자 인터페이스를 결정하면, 런타임에 사용자가 응용 프로그램에 관련된 데이터를 변경하고 저장할 수 있도록 데이터 소스에 해당 컨트롤을 바인딩할 수 있습니다.  
  
 Windows Forms의 컨트롤을 하나 또는 여러 개 바인딩할 때 <xref:System.Windows.Forms.BindingSource> 컨트롤을 폼의 컨트롤과 데이터 소스 사이를 이어주는 다리로 사용하면 바인딩이 가장 쉽게 이루어집니다.  
  
 폼에 있는 컨트롤을 한 개 이상 데이터에 바인딩할 수 있습니다. 다음 절차에서는 <xref:System.Windows.Forms.TextBox> 컨트롤이 데이터 소스에 바인딩됩니다.  
  
 이 절차에서는 데이터베이스에서 파생된 데이터 소스에 바인딩한다고 가정합니다.  다른 데이터 저장소에서 데이터 소스를 만드는 방법에 대한 자세한 내용은 [데이터 소스 개요](../Topic/Add%20new%20data%20sources.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에 컨트롤을 바인딩하려면  
  
1.  <xref:System.Windows.Forms.TextBox> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  **속성** 창에서 다음을 수행합니다.  
  
    1.  **\(DataBindings\)** 노드를 확장합니다.  
  
    2.  <xref:System.Windows.Forms.TextBox.Text%2A> 속성 옆의 화살표를 클릭합니다.  
  
         **DataSource** UI 형식 편집기가 열립니다.  
  
         이전에 프로젝트 또는 폼에 대해 구성한 데이터 소스가 있으면 해당 데이터 소스가 표시됩니다.  
  
3.  **프로젝트 데이터 소스 추가**를 클릭하여 데이터에 연결하고 데이터 소스를 만듭니다.  
  
4.  **데이터 소스 구성 마법사** 시작 페이지에서 **다음**을 클릭합니다.  
  
5.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택합니다.  
  
6.  **데이터 연결 선택** 페이지의 사용 가능한 연결 목록에서 데이터 연결을 선택합니다.  원하는 데이터 연결을 사용할 수 없으면 **새 연결**을 선택하여 새 데이터 연결을 만듭니다.  
  
7.  **예, 다음으로 연결을 저장합니다.**를 선택하여 응용 프로그램 구성 파일에 연결 문자열을 저장합니다.  
  
8.  응용 프로그램으로 가져올 데이터베이스 개체를 선택합니다.  이 경우에는 <xref:System.Windows.Forms.TextBox>에 표시할 테이블 필드를 선택합니다.  
  
9. 원하는 경우 기본 데이터 집합 이름을 바꿉니다.  
  
10. **마침**을 클릭합니다.  
  
11. **속성** 창에서 <xref:System.Windows.Forms.TextBox.Text%2A> 속성 옆의 화살표를 다시 클릭합니다.  **DataSource** UI 형식 편집기에서 <xref:System.Windows.Forms.TextBox>를 바인딩할 필드의 이름을 선택합니다.  
  
     **DataSource** UI 형식 편집기가 닫히고 데이터 집합인 <xref:System.Windows.Forms.BindingSource>와 해당 데이터 연결의 테이블 어댑터가 폼에 추가됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.BindingNavigator>   
 [데이터 소스 개요](../Topic/Add%20new%20data%20sources.md)   
 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)