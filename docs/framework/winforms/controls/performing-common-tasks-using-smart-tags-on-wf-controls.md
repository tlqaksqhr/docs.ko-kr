---
title: "연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2fb4e8bf710e55be0a817a4154dfbce114db191
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a>연습: Windows Forms 컨트롤에서 스마트 태그를 사용하여 일반 작업 수행
Windows Forms 응용 프로그램에 대 한 폼과 컨트롤을 구성할 때에 반복 해 서 수행 하는 많은 작업이 있습니다. 일반적으로 수행된 하는 작업 중 일부입니다.  
  
-   추가 / 제거를 탭 한 <xref:System.Windows.Forms.TabControl>합니다.  
  
-   부모 항목에 컨트롤을 도킹 합니다.  
  
-   방향을 변경는 <xref:System.Windows.Forms.SplitContainer> 제어 합니다.  
  
 개발 속도 많은 컨트롤을 디자인 타임에는 단일 제스처에 이와 같은 일반적인 태스크를 수행할 수 있도록 하는 상황에 맞는 메뉴 스마트 태그를 제공 합니다. 이러한 작업 라고 *스마트 태그 동사*합니다.  
  
 스마트 태그 한 디자이너의 수명 제어 인스턴스에 연결 된 유지와 항상 사용할 수 있습니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   스마트 태그를 사용 하 여  
  
-   설정 및 해제 스마트 태그  
  
 작업을 완료하면 이러한 중요한 레이아웃 기능이 수행하는 역할을 이해하게 됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  "SmartTagsExample" 이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다. 자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.  
  
2.  폼을 선택는 **Windows Forms 디자이너**합니다.  
  
## <a name="using-smart-tags"></a>스마트 태그를 사용 하 여  
 스마트 태그는 사용자에 게 제공 하는 컨트롤에 디자인 타임에 항상 사용할 수 있습니다.  
  
#### <a name="to-use-smart-tags"></a>스마트 태그를 사용 하려면  
  
1.  끌어서는 <xref:System.Windows.Forms.TabControl> 에서 **도구 상자** 폼으로 합니다. 스마트 태그 문자 모양을 확인 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))의 측면에 표시 되는 <xref:System.Windows.Forms.TabControl>합니다.  
  
2.  스마트 태그 문자 모양을 클릭 합니다. 문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 된 **탭 추가** 항목입니다. 새 탭 페이지에 추가 확인 된 <xref:System.Windows.Forms.TabControl>합니다.  
  
3.  끌어서는 <xref:System.Windows.Forms.TableLayoutPanel> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
4.  스마트 태그 문자 모양을 클릭 합니다. 문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 된 **열 추가** 항목입니다. 새 열에 추가 됩니다 확인는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.  
  
5.  끌어서는 <xref:System.Windows.Forms.SplitContainer> 에서 제어는 **도구 상자** 폼으로 합니다.  
  
6.  스마트 태그 문자 모양을 클릭 합니다. 문자 모양이 옆에 나타나는 바로 가기 메뉴에서 선택 된 **가로 분할자 방향** 항목입니다. 참조 하는 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 분할 막대는 이제 가로 방향으로 놓여 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [연습: Windows Forms 구성 요소에 스마트 태그를 추가합니다.](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
