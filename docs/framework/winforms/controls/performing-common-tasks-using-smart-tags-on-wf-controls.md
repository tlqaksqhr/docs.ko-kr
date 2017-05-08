---
title: "연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행 | Microsoft Docs"
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
  - "디자이너 작업"
  - "DesignerAction 개체 모델"
  - "스마트 태그"
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행
Windows Forms 응용 프로그램에 대한 폼과 컨트롤을 만들 때 반복적으로 수행되는 여러 작업이 있습니다.  일반적으로 수행되는 몇 가지 작업은 다음과 같습니다.  
  
-   <xref:System.Windows.Forms.TabControl>에서 탭 추가 또는 제거  
  
-   컨트롤을 해당 부모에 도킹  
  
-   <xref:System.Windows.Forms.SplitContainer> 컨트롤의 방향 변경  
  
 개발을 신속하게 할 수 있도록 여러 컨트롤에서 스마트 태그를 제공합니다. 스마트 태그는 상황에 맞는 메뉴로서 이를 사용하여 디자인 타임에 일반적인 작업들을 단일 동작으로 수행할 수 있습니다.  이러한 작업을 *스마트 태그 동사*라고 합니다.  
  
 스마트 태그는 디자이너에서 해당 수명 동안에 컨트롤 인스턴스와의 연결을 유지하며 항상 사용할 수 있습니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   스마트 태그 사용  
  
-   스마트 태그 활성화 및 비활성화  
  
 작업이 끝나면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해할 수 있게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### 프로젝트를 만들려면  
  
1.  "SmartTagsExample"이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.  자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  **Windows Forms 디자이너**에서 폼을 선택합니다.  
  
## 스마트 태그 사용  
 스마트 태그는 디자인 타임에 컨트롤에서 항상 사용할 수 있습니다.  
  
#### 스마트 태그를 사용하려면  
  
1.  **도구 상자**의 <xref:System.Windows.Forms.TabControl>을 폼으로 끌어 옵니다.  스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)이 <xref:System.Windows.Forms.TabControl>의 측면에 나타납니다.  
  
2.  스마트 태그 문자 모양을 클릭합니다.  스마트 태그 문자 모양 옆에 나타나는 바로 가기 메뉴에서 **탭 추가** 항목을 선택합니다.  새 탭 페이지가 <xref:System.Windows.Forms.TabControl>에 추가되었는지 확인합니다.  
  
3.  **도구 상자**의 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 끌어 옵니다.  
  
4.  스마트 태그 문자 모양을 클릭합니다.  스마트 태그 문자 모양 옆에 나타나는 바로 가기 메뉴에서 **열 추가** 항목을 선택합니다.  새 열이 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 추가되었는지 확인합니다.  
  
5.  **도구 상자**의 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 폼으로 끌어 옵니다.  
  
6.  스마트 태그 문자 모양을 클릭합니다.  스마트 태그 문자 모양 옆에 나타나는 바로 가기 메뉴에서 **가로 분할자 방향** 항목을 선택합니다.  <xref:System.Windows.Forms.SplitContainer> 컨트롤의 분할 막대가 이제 가로 방향으로 표시되는지 확인합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.TextBox>   
 <xref:System.Windows.Forms.TabControl>   
 <xref:System.Windows.Forms.SplitContainer>   
 <xref:System.ComponentModel.Design.DesignerActionList>   
 [Walkthrough: Adding Smart Tags to a Windows Forms Component](../Topic/Walkthrough:%20Adding%20Smart%20Tags%20to%20a%20Windows%20Forms%20Component.md)