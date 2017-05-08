---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.DataGridViewAddColumnDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView 컨트롤[Windows Forms], 열 추가"
  - "DataGridView 컨트롤[Windows Forms], 열 제거"
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 추가 및 제거
데이터를 표시하려면 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤에 열이 있어야 합니다.  컨트롤을 수동으로 채우려는 경우 열을 직접 추가해야 합니다.  또는 컨트롤을 데이터 소스에 바인딩하여 열이 자동으로 생성되고 채워지도록 할 수도 있습니다.  표시하려는 열보다 많은 열이 데이터 소스에 있는 경우 필요 없는 열을 제거할 수 있습니다.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자이너를 사용하여 열을 추가하려면  
  
1.  <xref:System.Windows.Forms.DataGridView> 컨트롤의 오른쪽 위 모퉁이에 있는 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭한 다음 **열 추가**를 선택합니다.  
  
2.  **열 추가** 대화 상자에서 **데이터 바인딩된 열** 옵션을 선택한 다음 데이터 소스의 열을 선택하거나 **바인딩되지 않은 열** 옵션을 선택하고 제공된 필드를 사용하여 해당 열을 정의합니다.  
  
3.  **추가** 단추를 클릭하여 해당 열을 추가하면 기존 열이 컨트롤 표시 영역에 아직 채워지지 않은 경우 추가된 열이 디자이너에 표시됩니다.  
  
    > [!NOTE]
    >  컨트롤의 스마트 태그에서 액세스할 수 있는 **열 편집** 대화 상자에서 열 속성을 수정할 수 있습니다.  
  
### 디자이너를 사용하여 열을 제거하려면  
  
1.  컨트롤의 스마트 태그에서 **열 편집**을 선택합니다.  
  
2.  **선택한 열** 목록에서 열을 선택합니다.  
  
3.  **제거** 단추를 클릭하여 열을 삭제하면 디자이너에서 열이 사라집니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)