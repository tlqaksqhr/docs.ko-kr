---
title: Visual Studio 응용 프로그램에 인쇄 가능한 보고서 추가
ms.date: 07/20/2015
helpviewer_keywords:
- printing [Visual Studio], reports
- reports [Visual Basic], printing in Visual Studio
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
ms.openlocfilehash: 4a7275a665e0c3290c2b3cd55c1af0c7cf0504f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="adding-printable-reports-to-visual-studio-applications"></a>Visual Studio 응용 프로그램에 인쇄 가능한 보고서 추가
Visual Studio는 다양 한 Visual Basic 응용 프로그램에 보고 하는 풍부한 데이터를 추가할 수 있도록 보고 솔루션을 지원 합니다. 만들 수 있으며 ReportViewer 컨트롤, Crystal Reports 또는 SQL Server Reporting Services를 사용 하 여 보고서를 추가할 수 없습니다.  
  
> [!NOTE]
>  SQL Server Reporting Services를 사용 하면 Visual Studio 대신 SQL Server 2005의 일부인 합니다. Reporting Services SQL Server 2005를 설치 하지 않은 경우 시스템에 설치 되지 않습니다.  
  
## <a name="overview-of-microsoft-reporting-technology-in-visual-basic-applications"></a>Visual Basic 응용 프로그램에 Microsoft 보고 기술을 개요  
 Microsoft 보고 기술을 응용 프로그램에서 사용 하려면 다음 방법 중 하나를 선택 합니다.  
  
-   Visual Basic Windows 응용 프로그램에 ReportViewer 컨트롤의 하나 이상의 인스턴스를 추가 합니다.  
  
-   보고서 서버 웹 서비스를 호출 하 여 프로그래밍 방식으로 SQL Server Reporting Services를 통합 합니다.  
  
-   사용 하 여 ReportViewer 컨트롤 및 Microsoft SQL Server 2005 Reporting Services 함께 보고서 뷰어 및 보고서 서버 보고서 처리기로 컨트롤을 사용 합니다. (Note: 보고서 서버와 ReportViewer 컨트롤 함께 사용 하려는 경우 SQL Server 2005 버전의 Reporting Services를 사용 해야) 합니다.  
  
## <a name="using-reportviewer-controls"></a>ReportViewer 컨트롤 사용  
 Visual Basic Windows 응용 프로그램에 보고서 기능을 포함 하는 가장 쉬운 방법은 응용 프로그램의 폼에 ReportViewer 컨트롤을 추가 하는 것입니다. 보고서 처리 기능을 응용 프로그램에 직접 추가 하 고 모든 ADO.NET 데이터 개체의 데이터를 사용 하 여 보고서를 작성할 수 있도록 통합된 보고서 디자이너가 제공 하는 컨트롤. 모든 기능을 갖춘 API 컨트롤에 대 한 프로그래밍 방식의 액세스를 제공 하 고 런타임 기능을 구성할 수 있도록를 보고 합니다.  
  
 ReportViewer는 기본 제공 보고서 처리 및 단일, 무료 배포 가능 데이터 컨트롤에 표시 되는 기능을 제공 합니다. 다음과 같은 보고서 기능이 필요한 경우 ReportViewer 컨트롤을 선택 합니다.  
  
-   보고서를 클라이언트 응용 프로그램에서 처리 합니다. 처리 된 보고서 컨트롤을 통해 제공 되는 보기 영역에 나타납니다.  
  
-   ADO.NET 데이터 테이블에 데이터 바인딩입니다. 사용 하는 보고서를 만들 수 <xref:System.Data.DataTable> 컨트롤에 제공 된 인스턴스. 비즈니스 개체에 직접 바인딩할 수 있습니다.  
  
-   응용 프로그램에 포함할 수 있는 재배포 가능한 컨트롤  
  
-   페이지 탐색, 인쇄, 검색 및 내보내기 형식 등과 같은 런타임 기능입니다. ReportViewer 도구 모음은 이러한 작업에 대 한 지원을 제공합니다.  
  
 ReportViewer 컨트롤을 사용 하려면에서 끌 수 있습니다는 **데이터** Visual Basic Windows 응용 프로그램의 폼으로 Visual Studio 도구 상자의 섹션.  
  
### <a name="creating-reports-in-visual-studio-for-reportviewer-controls"></a>ReportViewer 컨트롤에 대 한 Visual Studio에서 보고서 만들기  
 ReportViewer에 실행 되는 보고서를 작성 하려면 추가 **보고서** 템플릿을 프로젝트에 있습니다. Visual Studio 클라이언트 보고서 정의 파일 (.rdlc)를 만들어 프로젝트에 파일을 추가 하 고 Visual Studio 작업 영역에서 통합된 보고서 디자이너가 열립니다.  
  
 와 통합 되어 Visual Studio 보고서 디자이너는 **데이터 소스** 창. 필드를 끌 경우는 **데이터 소스** 창, 보고서 디자이너 보고서에 보고서 정의 파일에 데이터 원본에 대 한 메타 데이터를 복사 합니다. 이 메타 데이터를 자동으로 데이터 바인딩 코드를 생성할 ReportViewer 컨트롤에서 사용 됩니다.  
  
 Visual Studio 보고서 디자이너에서 보고서 미리 보기 기능을 포함 하지 않습니다. 보고서를 미리 보려면 응용 프로그램을 실행 하 고 항목에 포함 된 보고서를 미리 봅니다.  
  
|응용 프로그램에 기본 보고 기능을 추가 하려면|  
|---|    
|1.  ReportViewer 컨트롤을 끌어는 **데이터** 탭은 **도구 상자** 폼으로 합니다.<br />2.  **프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다. 에 **새 항목 추가** 대화 상자는 **보고서** 아이콘을 클릭 하 여 **추가**합니다.<br />     개발 환경에서 보고서 디자이너가 열리고 보고서 (.rdlc) 파일을 프로젝트에 추가 됩니다.<br />3.  보고서 항목을 끌어는 **도구 상자** 에서 보고서 레이아웃을 원하는 대로 정렬 합니다.<br />4.  필드를 끌어는 **데이터 소스** 보고서 레이아웃의 보고서 항목에는 창입니다.|  
  
## <a name="using-reporting-services-in-visual-basic-applications"></a>Visual Basic 응용 프로그램에서 Reporting Services를 사용 하 여  
 Reporting Services는 SQL Server와 함께 포함 되는 서버 기반 보고 기술입니다. Reporting Services ReportViewer 컨트롤에서 찾을 수 없는 추가 기능이 포함 됩니다. 다음과 같은 기능이 필요한 경우 Reporting Services를 선택 합니다.  
  
-   확장 배포 하 고 고용량 보고서 작업 및 복잡 한 또는 장기 실행 보고서에 대 한 향상 된 성능을 제공 하는 서버 쪽 보고서 처리 합니다.  
  
-   통합된 데이터 및 보고서 처리, 사용자 지정 보고서 컨트롤 및 서식 있는 출력 형식 렌더링에 대 한 지원.  
  
-   예약 된 보고서를 실행 하는 경우에 정확 하 게 지정할 수 있도록 보고서 처리 합니다.  
  
-   구독자 기반 보고서를 파일 공유 위치 또는 전자 메일을 통해 배포 합니다.  
  
-   필요에 따라 비즈니스 사용자가 보고서를 만들 수 있도록 보고서 작성 합니다.  
  
-   데이터 기반 구독을 동적 받는 사람 목록에 출력 하는 사용자 지정된 보고서를 라우팅할 합니다.  
  
-   데이터 처리, 보고서 배달, 사용자 지정 인증 및 보고서 렌더링에 대 한 사용자 지정 확장 합니다.  
  
 보고서 서버 웹 서비스로 구현 됩니다. 응용 프로그램 코드는 보고서 및 기타 메타 데이터에 액세스 하는 웹 서비스에 대 한 호출을 포함 해야 합니다. 웹 서비스는 보고서 서버 인스턴스에 대 한 전체 프로그래밍 방식 액세스를 제공합니다.  
  
 Reporting Services는 웹 기반 보고 기술 이기 때문에 기본 뷰어가 렌더링 된 보고서에 HTML 형식으로 표시 합니다. 기본 보고서 표시 형식으로 HTML을 사용 하지 않을 경우에 응용 프로그램에 대 한 사용자 지정 보고서 뷰어를 작성 해야 합니다.  
  
### <a name="creating-reports-in-visual-studio-for-reporting-services"></a>보고 서비스에 대 한 Visual Studio에서 보고서 만들기  
 보고서 서버에서 실행 되는 보고서를 작성 하려면 보고서 정의 (.rdl) 파일 만듭니다 Business Intelligence Development Studio를 통해 Visual Studio에서 SQL Server 2005에 포함 되어 있는.  
  
> [!NOTE]
>  SQL Server 2005를 SQL Server Reporting Services 및 Business Intelligence Development Studio를 사용 하려면 설치 되어 있어야 합니다.  
  
 Business Intelligence Development Studio에는 SQL Server 구성 요소에만 적용 되는 프로젝트 템플릿을 추가 합니다. 보고서를 만들려면에서 선택할 수 있습니다는 **보고서 서버 프로젝트** 또는 **보고서 서버 프로젝트 마법사** 템플릿. 데이터 원본 연결 및 쿼리 데이터 원본 유형, SQL Server, Oracle, Analysis Services, XML, SQL Server Integration Services 등의 다양 한을 지정할 수 있습니다. A **데이터** 탭 **레이아웃** 탭 및 **미리 보기** 탭을 사용 하면 데이터를 정의 하 고, 보고서 레이아웃을 만들고, 모두 동일한 작업 영역에서에서 보고서를 미리 볼 수 있도록 합니다.  
  
 컨트롤 또는 보고서 서버에 대 한 작성 하는 보고서 정의 두 기술 모두에서 재사용할 수 있습니다.  
  
|보고서 서버에서 실행 되는 보고서를 만들려면|  
|---|    
|1.  에 **파일** 메뉴 선택 **새로**합니다.<br />     **새 프로젝트** 대화 상자가 열립니다.<br />2.  에 **프로젝트 형식** 창에서 클릭 **비즈니스 인텔리전스 프로젝트**합니다.<br />3.  템플릿 창에서 선택 **보고서 서버 프로젝트** 또는 **보고서 서버 프로젝트 마법사**합니다.|  
  
## <a name="using-reportviewer-controls-and-sql-server-reporting-services-together"></a>ReportViewer 컨트롤 및 SQL Server Reporting Services를 함께 사용 하 여  
 ReportViewer 컨트롤 및 SQL Server 2005 Reporting Services는 동일한 응용 프로그램에서 함께 사용할 수 있습니다.  
  
-   ReportViewer 컨트롤은 응용 프로그램에서 보고서를 표시 하는 데 사용 되는 뷰어를 제공 합니다.  
  
-   Reporting Services 보고서를 제공 하 고 원격 서버의 모든 처리를 수행 합니다.  
  
 ReportViewer 컨트롤은 원격 Reporting Services 보고서 서버에 저장 되 고 처리 하는 보고서를 표시 하도록 구성할 수 있습니다. 이러한 유형의 구성 라고 *원격 처리 모드*합니다. 원격 처리 모드 컨트롤 원격 보고서 서버에 저장 된 보고서를 요청 합니다. 보고서 서버는 모든 보고서 처리, 데이터 처리 및 보고서 렌더링을 수행합니다. 완료, 렌더링 된 보고서 컨트롤에 반환 하 고 보기 영역에 표시 됩니다.  
  
 내보내기 형식, 매개 변수화 구현이 다른 보고서, 보고서 서버에서 사용할 수 있으며에서 역할 기반 권한 부여 모델을 통해 액세스 하는 데이터 원본 유형을 사용 하 여 추가 보고서 서버 지원에 실행 되는 보고서는 보고서 서버입니다.  
  
 원격 처리 모드를 사용 하려면 ReportViewer 컨트롤을 구성할 때 URL과 서버 보고서에 대 한 경로 지정 합니다.
