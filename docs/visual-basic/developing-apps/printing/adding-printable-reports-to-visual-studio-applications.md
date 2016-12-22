---
title: "Adding Printable Reports to Visual Studio Applications | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "printing [Visual Studio], reports"
  - "reports, printing in Visual Studio"
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Adding Printable Reports to Visual Studio Applications
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Visual Studio에서 지원하는 다양한 보고 솔루션을 통해 Visual Basic 응용 프로그램에 다양한 데이터 보고 기능을 추가할 수 있습니다.  ReportViewer 컨트롤, Crystal Reports 또는 SQL Server Reporting Services를 사용하여 보고서를 만들고 추가할 수 있습니다.  
  
> [!NOTE]
>  SQL Server Reporting Services는 Visual Studio가 아닌 SQL Server 2005의 일부입니다.  SQL Server 2005가 설치되어 있지 않으면 Reporting Services가 설치되지 않습니다.  
  
## Visual Basic 응용 프로그램의 Microsoft 보고 기술 개요  
 다음과 같은 방법으로 응용 프로그램에 Microsoft 보고 기술을 사용할 수 있습니다.  
  
-   Visual Basic Windows 응용 프로그램에 ReportViewer 컨트롤의 인스턴스를 하나 이상 추가합니다.  
  
-   Report Server 웹 서비스를 호출하여 Integrate SQL Server Reporting Services를 프로그래밍 방식으로 통합합니다.  
  
-   ReportViewer 컨트롤과 Microsoft SQL Server 2005 Reporting Services를 함께 사용합니다. 이 경우 컨트롤은 보고서 뷰어로 사용되고 보고서 서버는 보고서 프로세서로 사용됩니다.  보고서 서버와 ReportViewer 컨트롤을 함께 사용하려면 SQL Server 2005 버전의 Reporting Services를 사용해야 합니다.  
  
## ReportViewer 컨트롤 사용  
 Visual Basic Windows 응용 프로그램에 보고 기능을 추가하는 가장 쉬운 방법은 응용 프로그램의 폼에 ReportViewer 컨트롤을 추가하는 것입니다.  이 컨트롤은 보고서 처리 기능을 응용 프로그램에 직접 추가하고 통합된 보고서 디자이너를 제공하므로 사용자가 임의의 ADO.NET 데이터 개체에 포함된 데이터를 사용하여 보고서를 빌드할 수 있습니다.  모든 기능을 갖춘 API를 사용하면 컨트롤과 보고서에 프로그래밍 방식으로 액세스하여 런타임 기능을 구성할 수 있습니다.  
  
 ReportViewer는 자유롭게 배포할 수 있는 단일 데이터 컨트롤을 통해 보고서 처리 및 표시 기능을 기본 제공합니다.  다음과 같은 보고 기능이 필요한 경우 ReportViewer 컨트롤을 선택합니다.  
  
-   클라이언트 응용 프로그램에서 보고서 처리.  처리된 보고서는 컨트롤에서 제공하는 뷰 영역에 표시됩니다.  
  
-   ADO.NET 데이터 테이블에 데이터 바인딩.  컨트롤에 제공되는 <xref:System.Data.DataTable> 인스턴스를 사용하는 보고서를 만들 수 있습니다.  비즈니스 개체에 직접 바인딩할 수도 있습니다.  
  
-   응용 프로그램에 포함할 수 있는 재배포 가능 컨트롤  
  
-   페이지 탐색, 인쇄, 검색 및 내보내기 형식 등과 같은 런타임 기능.  ReportViewer 도구 모음에서는 이러한 작업을 지원합니다.  
  
 ReportViewer 컨트롤을 사용하려면 Visual Studio 도구 상자의 **데이터** 섹션에서 이 컨트롤을 끌어 Visual Basic Windows 응용 프로그램의 폼에 놓습니다.  
  
### Visual Studio에서 ReportViewer 컨트롤에 대한 보고서 만들기  
 ReportViewer에서 실행되는 보고서를 빌드하려면 프로젝트에 **보고서** 템플릿을 추가합니다.  Visual Studio는 클라이언트 보고서 정의 파일\(.rdlc\)을 만들고 이 파일을 프로젝트에 추가한 다음 Visual Studio 작업 영역에서 통합된 보고서 디자이너를 엽니다.  
  
 Visual Studio 보고서 디자이너는 **데이터 소스** 창과 통합됩니다.  사용자가 **데이터 소스** 창에서 필드를 보고서로 끌면 보고서 디자이너는 데이터 소스에 대한 메타데이터를 보고서 정의 파일에 복사합니다.  ReportViewer 컨트롤에서는 이 메타데이터를 사용하여 자동으로 데이터 바인딩 코드를 생성합니다.  
  
 Visual Studio 보고서 디자이너에는 보고서 미리 보기 기능이 없습니다.  보고서를 미리 보려면 응용 프로그램을 실행하여 응용 프로그램에 포함된 보고서를 미리 보십시오.  
  
||  
|-|  
|응용 프로그램에 기본 보고 기능을 추가하려면|  
|1.  **도구 상자**의 **데이터** 탭에서 ReportViewer 컨트롤을 폼으로 끌어 옵니다.<br />2.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.  **새 항목 추가** 대화 상자에서 **보고서** 아이콘을 선택한 다음 **추가**를 클릭합니다.<br />     개발 환경에서 보고서 디자이너가 열리고 보고서 파일\(.rdlc\)이 프로젝트에 추가됩니다.<br />3.  **도구 상자**에서 보고서 레이아웃으로 보고서 항목을 끌어 와서 원하는 대로 배치합니다.<br />4.  **데이터 소스** 창에서 보고서 레이아웃의 보고서 항목으로 필드를 끌어 놓습니다.|  
  
## Visual Basic 응용 프로그램에서 Reporting Services 사용  
 Reporting Services는 SQL Server에 포함된 서버 기반 보고 기술입니다.  Reporting Services에는 ReportViewer 컨트롤에 없는 기능이 추가로 들어 있습니다.  다음과 같은 기능이 필요한 경우 Reporting Services를 선택합니다.  
  
-   복잡하거나 실행하는 데 시간이 오래 걸리는 보고서 및 분량이 많은 보고서 작업을 하는 데 향상된 성능을 제공하는 확장된 배포 및 서버 쪽 보고서 처리  
  
-   사용자 지정 보고서 컨트롤과 풍부한 렌더링 출력 형식을 지원하는 통합된 데이터 및 보고서 처리  
  
-   보고서가 실행될 시기를 정확하게 지정할 수 있는 예약된 보고서 처리  
  
-   전자 메일이나 파일 공유 위치를 통한 구독자 기반 보고서 배포  
  
-   비즈니스 사용자가 필요로 하는 보고서를 만들 수 있는 특별 보고  
  
-   받는 사람의 동적 목록에 사용자 지정된 보고서 출력을 라우팅하는 데이터 기반 구독  
  
-   데이터 처리, 보고서 전달, 사용자 지정 인증 및 보고서 렌더링을 위한 사용자 지정 확장  
  
 보고서 서버는 웹 서비스로 구현됩니다.  보고서 및 기타 메타데이터에 액세스하려면 응용 프로그램 코드에서 웹 서비스를 호출해야 합니다.  웹 서비스는 보고서 서버 인스턴스에 대한 완벽한 프로그래밍 방식의 액세스를 제공합니다.  
  
 Reporting Services는 웹 기반 보고 기술이므로 기본 뷰어에서 보고서를 HTML 형식으로 렌더링하여 표시합니다.  기본 보고서 표시 형식으로 HTML을 사용하지 않으려면 응용 프로그램에 대한 사용자 지정 보고서 뷰어를 직접 작성해야 합니다.  
  
### Visual Studio에서 Reporting Services에 대한 보고서 만들기  
 보고서 서버에서 실행되는 보고서를 빌드하려면 SQL Server 2005에 포함된 Business Intelligence Development Studio를 통해 Visual Studio에서 보고서 정의 파일\(.rdl\)을 만듭니다.  
  
> [!NOTE]
>  SQL Server Reporting Services와 Business Intelligence Development Studio를 사용하려면 SQL Server 2005가 설치되어 있어야 합니다.  
  
 Business Intelligence Development Studio는 SQL Server 구성 요소에 사용되는 프로젝트 템플릿을 추가합니다.  보고서를 만들려면 **보고서 서버 프로젝트** 또는 **보고서 서버 프로젝트 마법사** 템플릿을 선택합니다.  SQL Server, Oracle, Analysis Services, XML 및 SQL Server Integration Services를 비롯한 여러 가지 데이터 소스 형식에 대한 데이터 소스 연결 및 쿼리를 지정할 수 있습니다.  **데이터** 탭, **레이아웃** 탭 및 **미리 보기** 탭을 사용하여 데이터를 정의하고, 보고서 레이아웃을 만들고, 모든 보고서를 동일한 작업 영역에서 미리 볼 수 있습니다.  
  
 컨트롤이나 보고서 서버에 대해 빌드한 보고서 정의는 두 기술 모두에서 다시 사용할 수 있습니다.  
  
||  
|-|  
|보고서 서버에서 실행되는 보고서를 만들려면|  
|1.  **파일** 메뉴에서 **새로 만들기**를 선택합니다.<br />     **새 프로젝트** 대화 상자가 열립니다.<br />2.  **프로젝트 형식** 창에서 **비즈니스 인텔리전스 프로젝트**를 클릭합니다.<br />3.  템플릿 창에서 **보고서 서버 프로젝트** 또는 **보고서 서버 프로젝트 마법사**를 선택합니다.|  
  
## ReportViewer 컨트롤과 SQL Server Reporting Services를 함께 사용  
 ReportViewer 컨트롤과 SQL Server 2005 Reporting Services를 동일한 응용 프로그램에서 함께 사용할 수 있습니다.  
  
-   ReportViewer 컨트롤은 응용 프로그램에 보고서를 표시하는 데 사용되는 뷰어를 제공합니다.  
  
-   Reporting Services는 보고서를 제공하고 원격 서버에서 모든 처리를 수행합니다.  
  
 원격 Reporting Services 보고서 서버에서 저장 및 처리되는 보고서를 표시하도록 ReportViewer 컨트롤을 구성할 수 있습니다.  이런 구성을 *원격 처리 모드*라고 합니다.  원격 처리 모드에서 컨트롤은 원격 보고서 서버에 저장된 보고서를 요청합니다.  보고서 서버는 보고서 처리, 데이터 처리 및 보고서 렌더링 작업을 모두 수행합니다.  렌더링하여 완성된 보고서는 컨트롤에 반환되고 뷰 영역에 표시됩니다.  
  
 보고서 서버에서 실행되는 보고서는 추가 내보내기 형식을 지원하며, 보고서 매개 변수화를 다른 방식으로 구현할 수 있고, 보고서 서버에서 지원하는 데이터 소스 형식을 사용합니다. 이 보고서에는 보고서 서버의 역할 기반 권한 부여 모델을 통해 액세스할 수 있습니다.  
  
 원격 처리 모드를 사용하려면 ReportViewer 컨트롤을 구성할 때 서버 보고서에 대한 경로와 URL을 지정합니다.