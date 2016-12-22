---
title: "Windows Forms Application Basics (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Windows applications"
  - "Windows Forms, Visual Basic"
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Windows Forms Application Basics (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]의 중요한 기능 중 하나는 사용자의 컴퓨터에서 로컬로 실행되는 Windows Forms 응용 프로그램을 만드는 것입니다.  Visual Studio만들다Windows Forms을 사용 하 여응용 프로그램및사용자인터페이스사용 하면 됩니다.   Windows Forms 응용 프로그램은 <xref:System.Windows.Forms> 네임스페이스의 클래스를 기반으로 합니다.  
  
## Windows Forms 응용 프로그램 디자인  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]를 사용하여 Windows Forms 및 Windows 서비스 응용 프로그램을 만들 수 있습니다.  자세한 내용은 다음 항목을 참조하십시오.  
  
-   [Windows Forms 시작](../Topic/Getting%20Started%20with%20Windows%20Forms.md).  Windows Forms을 만들고 프로그래밍하는 방법에 대한 정보를 제공합니다.  
  
-   [Windows Forms Walkthroughs](http://msdn.microsoft.com/ko-kr/fd44d13d-4733-416f-aefc-32592e59e5d9).  Windows Forms을 기반으로 Windows Forms 응용 프로그램을 만드는 일반적인 개발 방법에 대해 단계별로 설명하는 항목들을 제공합니다.  
  
-   [Windows Forms 컨트롤](../Topic/Windows%20Forms%20Controls.md).  Windows Forms 컨트롤의 사용에 대해 설명하는 항목의 모음입니다.  
  
-   [Windows Service Applications](../Topic/Developing%20Windows%20Service%20Applications.md).  Windows 서비스를 만드는 방법을 설명하는 항목을 나열합니다.  
  
## 다양한 기능의 대화형 사용자 인터페이스 만들기  
 Windows Forms은 파일 시스템 읽기 및 쓰기 등과 같은 일반적인 응용 프로그램 작업을 가능하게 하는 관리되는 라이브러리 집합으로 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]의 스마트 클라이언트 구성 요소입니다.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]와 같은 개발 환경을 사용하면 정보를 표시하고, 사용자에게 입력을 요청하고, 네트워크를 통해 원격 컴퓨터와 통신하는 Windows Forms 응용 프로그램을 만들 수 있습니다.  
  
 Windows Forms에서 폼은 사용자에게 정보를 표시할 수 있는 시각적 화면입니다.  일반적으로 폼에 컨트롤을 배치하고 마우스 클릭이나 키 누름 등과 같은 사용자 동작에 대한 응답을 개발하는 방식으로 Windows Forms 응용 프로그램을 만듭니다.  *컨트롤*은 데이터를 표시하거나 데이터 입력을 받아들이는 개별적인 UI\(사용자 인터페이스\) 요소입니다.  
  
### 이벤트  
 사용자가 폼 또는 폼의 컨트롤 중 하나에 대해 어떤 동작을 수행하면 이벤트가 발생합니다.  응용 프로그램에서는 코드를 사용하여 이러한 이벤트에 반응하고 이벤트가 발생한 경우 이벤트를 처리합니다.  자세한 내용은 [Windows Forms에서 이벤트 처리기 만들기](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)를 참조하십시오.  
  
### 컨트롤  
 Windows Forms에는 폼에 배치할 수 있는 다양한 컨트롤이 포함됩니다. 이러한 컨트롤로는 텍스트 상자, 단추, 드롭다운 상자, 라디오 단추 및 웹 페이지를 표시하는 컨트롤이 있습니다.  폼에 사용할 수 있는 모든 컨트롤의 목록을 보려면 [Windows Forms에 사용할 수 있는 컨트롤](../Topic/Controls%20to%20Use%20on%20Windows%20Forms.md)을 참조하십시오.  기존 컨트롤 중에 적합한 컨트롤이 없는 경우 Windows Forms에서는 <xref:System.Windows.Forms.UserControl> 클래스를 사용하여 사용자 지정 컨트롤을 직접 만들 수 있도록 지원합니다.  
  
 Windows Forms에는 Microsoft Office와 같은 고급 응용 프로그램의 기능을 에뮬레이트하는 다양한 UI 컨트롤이 있습니다.  <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하면 텍스트와 이미지가 포함되고, 하위 메뉴를 표시하며, 텍스트 상자와 콤보 상자 등의 다른 컨트롤을 호스팅하는 도구 모음과 메뉴를 만들 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 끌어서 놓기 폼 디자이너를 사용하면 커서로 컨트롤을 선택하여 폼의 원하는 위치에 놓기만 하는 방식으로 Windows Forms 응용 프로그램을 쉽게 만들 수 있습니다.  디자이너에서는 모눈선 및 맞춤선 등과 같은 도구를 제공하므로 컨트롤을 쉽게 배치할 수 있습니다.  또한 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]를 사용하든 명령줄에서 컴파일하든 상관없이 <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> 및 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 사용하여 최소의 시간과 노력으로 고급 폼 레이아웃을 만들 수 있습니다.  
  
### 사용자 지정 UI 요소  
 마지막으로, 사용자 지정 UI 요소를 직접 만들어야 하는 경우 <xref:System.Drawing> 네임스페이스에는 선, 원 및 기타 도형을 폼에 직접 렌더링하는 데 필요한 모든 클래스가 포함되어 있습니다.  
  
 이러한 기능을 사용하는 데 대한 단계별 정보를 보려면 다음 도움말 항목을 참조하십시오.  
  
|To|참조|  
|--------|--------|  
|[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]를 사용하여 새 Windows Forms 응용 프로그램 만들기|[Walkthrough: Creating a Simple Windows Form](http://msdn.microsoft.com/ko-kr/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|폼에서 컨트롤 사용|[방법: Windows Forms에 컨트롤 추가](../Topic/How%20to:%20Add%20Controls%20to%20Windows%20Forms.md)|  
|폼 및 폼의 컨트롤에서 발생하는 이벤트 처리|[How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/ko-kr/8461e9b8-14e8-406f-936e-3726732b23d2)|  
|<xref:System.Windows.Forms.ToolStrip> 컨트롤 사용|[How to: Create a Basic ToolStrip with Standard Items Using the Designer](../Topic/How%20to:%20Create%20a%20Basic%20Windows%20Forms%20ToolStrip%20with%20Standard%20Items%20Using%20the%20Designer.md)|  
|<xref:System.Drawing>을 사용하여 그래픽 만들기|[그래픽 프로그래밍 시작](../Topic/Getting%20Started%20with%20Graphics%20Programming.md)|  
|사용자 지정 컨트롤 만들기|[방법: UserControl 클래스에서 상속](../Topic/How%20to:%20Inherit%20from%20the%20UserControl%20Class.md)|  
  
## 데이터 표시 및 조작  
 데이터베이스, XML 파일, XML Web service 또는 기타 데이터 소스의 데이터를 표시해야 하는 응용 프로그램이 많습니다.  Windows Forms에서는 기존의 행과 열 형식에 이러한 테이블 형식 데이터를 렌더링하여 모든 데이터를 각각 별도의 셀에 표시하기 위해 <xref:System.Windows.Forms.DataGridView>라는 유연한 컨트롤을 제공합니다.  <xref:System.Windows.Forms.DataGridView>를 사용하면 개별 셀의 모양을 사용자 지정하고, 임의의 행과 열을 고정하고, 복잡한 컨트롤을 셀 안에 표시하는 등의 작업을 할 수 있습니다.  
  
 네트워크를 통해 데이터 소스에 연결하는 작업은 Windows Forms 스마트 클라이언트를 사용하면 간단하게 수행할 수 있습니다.  [!INCLUDE[vsprvslong](../../../csharp/misc/includes/vsprvslong_md.md)] 및 [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)]의 Windows Forms에 새로 추가된 <xref:System.Windows.Forms.BindingSource> 구성 요소는 데이터 소스에 대한 연결을 나타내며, 데이터를 컨트롤에 바인딩하고 이전 레코드 및 다음 레코드로 이동하고 레코드를 편집하고 변경 내용을 원래의 소스로 저장하는 메서드를 노출합니다.  <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 사용자가 레코드 간을 이동할 수 있도록 <xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 간단한 인터페이스를 제공합니다.  
  
### 데이터 바인딩된 컨트롤  
 데이터베이스, 웹 서비스 및 프로젝트의 개체 등과 같은 데이터 소스를 표시하는 데이터 소스 창을 사용하면 데이터 바인딩된 컨트롤을 쉽게 만들 수 있습니다.  이 창의 항목을 프로젝트의 폼으로 끌어서 놓아 데이터 바인딩된 컨트롤을 만들 수 있습니다.  또한 데이터 소스 창의 개체를 기존 컨트롤로 끌어서 놓아 기존 컨트롤을 데이터에 바인딩할 수도 있습니다.  
  
### 설정  
 Windows Forms에서 관리할 수 있는 다른 형식의 데이터 바인딩으로 설정이 있습니다.  대부분의 스마트 클라이언트 응용 프로그램은 마지막으로 알려진 폼 크기와 같은 런타임 상태에 대한 정보를 유지하고 저장된 파일의 기본 위치 등과 같은 사용자 기본 설정 데이터를 유지해야 합니다.  응용 프로그램 설정 기능은 이 두 가지 형식의 설정을 모두 클라이언트 컴퓨터에 저장하는 쉬운 방법을 제공함으로써 이러한 요구 사항을 해결합니다.  이들 설정이 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 또는 코드 편집기를 통해 정의되면 XML로 유지되며 런타임에 자동으로 메모리로 로드됩니다.  
  
 이러한 기능을 사용하는 데 대한 단계별 정보를 보려면 다음 도움말 항목을 참조하십시오.  
  
|To|참조|  
|--------|--------|  
|<xref:System.Windows.Forms.BindingSource> 구성 요소 사용|[방법: 디자이너를 사용하여 Windows Forms 컨트롤에 BindingSource 구성 요소 바인딩](../Topic/How%20to:%20Bind%20Windows%20Forms%20Controls%20with%20the%20BindingSource%20Component%20Using%20the%20Designer.md)|  
|[!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] 데이터 소스 사용|[방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링](../Topic/How%20to:%20Sort%20and%20Filter%20ADO.NET%20Data%20with%20the%20Windows%20Forms%20BindingSource%20Component.md)|  
|데이터 소스 창 사용|[연습: Windows Form에 데이터 표시](../Topic/Walkthrough:%20Displaying%20Data%20on%20a%20Windows%20Form.md)|  
|응용 프로그램 설정 사용|[How to: Create Application Settings Using the Designer](http://msdn.microsoft.com/ko-kr/53b3af80-1c02-4e35-99c6-787663148945)|  
  
## 응용 프로그램을 클라이언트 컴퓨터에 배포  
 응용 프로그램을 작성한 다음에는 이를 사용자에게 보내 사용자가 자신의 클라이언트 컴퓨터에 설치하고 실행할 수 있도록 해야 합니다.  [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 기술을 사용하면 몇 번의 클릭만으로 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 내에서 응용 프로그램을 배포할 수 있고 웹에 있는 응용 프로그램을 가리키는 URL을 사용자에게 제공할 수 있습니다.  [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]는 응용 프로그램의 모든 요소 및 종속성을 관리하고 응용 프로그램이 클라이언트 컴퓨터에 올바로 설치되도록 합니다.  
  
 사용자가 네트워크에 연결되어 있을 때만 실행되거나 온라인과 오프라인에서 모두 실행되도록 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 응용 프로그램을 구성할 수 있습니다.  응용 프로그램이 오프라인 작업을 지원하도록 지정하면 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]는 사용자가 URL을 사용하지 않고도 응용 프로그램을 열 수 있도록 사용자의 **시작** 메뉴에 응용 프로그램에 대한 링크를 추가합니다.  
  
 응용 프로그램을 업데이트할 경우 새 배포 매니페스트 및 응용 프로그램의 새 복사본을 웹 서버에 게시하게 됩니다.  [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]는 사용 가능한 업데이트가 있는지 검색하고 사용자의 설치를 업그레이드하므로 이전 어셈블리를 업데이트하는 데 사용자 지정 프로그래밍이 필요하지 않습니다.  
  
 [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]에 대한 자세한 소개는 [ClickOnce 보안 및 배포](/visual-studio/deployment/clickonce-security-and-deployment)를 참조하십시오.  이러한 기능을 사용하는 데 대한 단계별 정보를 보려면 다음 도움말 항목을 참조하십시오.  
  
|To|참조|  
|--------|--------|  
|[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]를 사용하여 응용 프로그램 배포|[방법: 게시 마법사를 사용하여 ClickOnce 응용 프로그램 게시](../Topic/How%20to:%20Publish%20a%20ClickOnce%20Application%20using%20the%20Publish%20Wizard.md)<br /><br /> [연습: ClickOnce 응용 프로그램 수동 배포](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md)|  
|[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] 배포 업데이트|[방법: ClickOnce 응용 프로그램에 대한 업데이트 관리](../Topic/How%20to:%20Manage%20Updates%20for%20a%20ClickOnce%20Application.md)|  
|[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]를 사용하여 보안 관리|[방법: ClickOnce 보안 설정 사용](../Topic/How%20to:%20Enable%20ClickOnce%20Security%20Settings.md)|  
  
## 기타 컨트롤 및 기능  
 이외에도 Windows Forms에는 대화 상자 만들기, 인쇄, 도움말과 설명서 추가, 프로그램을 여러 언어로 지역화 등과 같은 일반적인 작업을 쉽고 빠르게 수행하는 데 도움이 되는 여러 기능이 있습니다.  또한 Windows Forms에서는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]의 강력한 보안 시스템을 사용하므로 고객에게 더욱 안전한 응용 프로그램을 제공할 수 있습니다.  
  
 이러한 기능을 사용하는 데 대한 단계별 정보를 보려면 다음 도움말 항목을 참조하십시오.  
  
|To|참조|  
|--------|--------|  
|폼의 내용 인쇄|[방법: Windows Forms의 그래픽 인쇄](../Topic/How%20to:%20Print%20Graphics%20in%20Windows%20Forms.md)<br /><br /> [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](../Topic/How%20to:%20Print%20a%20Multi-Page%20Text%20File%20in%20Windows%20Forms.md)|  
|Windows Forms 응용 프로그램 전역화|[Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5)|  
|Windows Forms 보안에 대한 자세한 내용|[Windows Forms의 보안 개요](../Topic/Security%20in%20Windows%20Forms%20Overview.md)|  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Windows Forms 개요](../Topic/Windows%20Forms%20Overview.md)   
 [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)