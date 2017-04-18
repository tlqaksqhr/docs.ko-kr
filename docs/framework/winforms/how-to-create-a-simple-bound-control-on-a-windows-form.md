---
title: "방법: Windows Form에 단순 바인딩된 컨트롤 만들기 | Microsoft Docs"
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
  - "데이터 바인딩, 단순 데이터 바인딩"
  - "Windows Forms 컨트롤, 데이터 바인딩"
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: Windows Form에 단순 바인딩된 컨트롤 만들기
*단순 바인딩*을 사용하면 데이터 집합 테이블에 있는 열 값과 같은 단일 데이터 요소를 컨트롤에 표시할 수 있습니다.  컨트롤의 모든 속성을 데이터 값에 단순 바인딩할 수 있습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤을 단순 바인딩하려면  
  
1.  데이터 소스에 연결합니다.  자세한 내용은 [데이터 소스에 연결](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)을 참조하십시오.  
  
2.  폼에서 컨트롤을 선택하고 **속성** 창을 표시합니다.  
  
3.  **\(DataBindings\)** 속성을 확장합니다.  
  
     가장 자주 바인딩되는 속성이 **\(DataBindings\)** 속성 아래에 표시됩니다.  예를 들면 대부분의 컨트롤에서 **Text** 속성이 가장 자주 바인딩되는 속성입니다.  
  
4.  바인딩할 속성이 일반적인 바인딩 속성 중 하나가 아닌 경우 **\(고급\)** 상자의 **줄임표** 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭하여 해당 컨트롤의 전체 속성 목록이 있는 **서식 지정 및 고급 바인딩** 대화 상자를 표시합니다.  
  
5.  바인딩할 속성을 선택하고 **바인딩** 아래의 드롭다운 화살표를 클릭합니다.  
  
     사용할 수 있는 데이터 소스 목록이 표시됩니다.  
  
6.  바인딩할 데이터 소스를 원하는 단일 데이터 요소를 찾을 때까지 확장합니다.  예를 들어, 데이터 집합 테이블에 있는 열 값에 바인딩할 경우 해당 데이터 집합의 이름을 확장한 다음 테이블 이름을 확장하여 열 이름을 표시합니다.  
  
7.  바인딩할 요소 이름을 클릭합니다.  
  
8.  **서식 지정 및 고급 바인딩** 대화 상자에서 작업하는 경우 **확인**을 클릭하여 **속성** 창으로 돌아갑니다.  
  
9. 컨트롤의 추가 속성을 바인딩하려면 3단계에서 7단계까지 반복합니다.  
  
    > [!NOTE]
    >  단순 데이터 바인딩은 데이터 요소 하나만 표시하므로 단순 바인딩된 컨트롤을 가진 Windows Form에서는 탐색 논리를 포함시키는 것이 일반적입니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Binding>   
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)