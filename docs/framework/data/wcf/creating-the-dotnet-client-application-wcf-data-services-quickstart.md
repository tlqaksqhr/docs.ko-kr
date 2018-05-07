---
title: .NET Framework 클라이언트 응용 프로그램 만들기(WCF Data Services 빠른 시작)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 09981a7aee2db24d8464bbc7412b82a57ec8115b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>.NET Framework 클라이언트 응용 프로그램 만들기(WCF Data Services 빠른 시작)
이것은의 마지막 작업은 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 빠른 시작 합니다. 이 작업에서는 솔루션에 콘솔 응용 프로그램을 추가에 대 한 참조를 추가 합니다는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 이 새 클라이언트 응용 프로그램 및 액세스에 공급 된 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 생성 된 클라이언트 데이터 서비스 클래스와 클라이언트를 사용 하 여 클라이언트 응용 프로그램에서 피드 라이브러리입니다.  
  
> [!NOTE]
>  데이터 피드에 액세스하기 위해 .NET Framework 기반 클라이언트 응용 프로그램이 필요하지는 않습니다. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 사용하는 모든 응용 프로그램 구성 요소에서 데이터 서비스에 액세스할 수 있습니다. 자세한 내용은 참조 [클라이언트 응용 프로그램에서 데이터 서비스를 사용 하 여](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)합니다.  
  
### <a name="to-create-the-client-application-by-using-visual-studio"></a>Visual Studio를 사용하여 클라이언트 응용 프로그램을 만들려면  
  
1.  **솔루션 탐색기**솔루션을 마우스 오른쪽 단추로 클릭 하 여 **추가**, 클릭 하 고 **새 프로젝트**합니다.  
  
2.  **프로젝트 형식**, 클릭 **Windows**를 선택한 후 **WPF 응용 프로그램** 에 **템플릿** 창.  
  
3.  입력 `NorthwindClient` 프로젝트 이름과 클릭 한 다음에 대 한 **확인**합니다.  
  
4.  MainWindow.xaml 파일을 열고 XAML 코드를 다음 코드로 바꿉니다.  
  
     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]  
  
### <a name="to-add-a-data-service-reference-to-the-project"></a>프로젝트에 데이터 서비스 참조를 추가하려면  
  
1.  NorthwindClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 여, **서비스 참조 추가**, 클릭 하 고 **Discover**합니다.  
  
     첫 번째 작업에서 만든 Northwind 데이터 서비스가 표시됩니다.  
  
2.  에 **Namespace** 텍스트 상자에서 `Northwind`, 클릭 하 고 **확인**합니다.  
  
     데이터 서비스 리소스에 개체로 액세스하고 상호 작용하는 데 사용되는 데이터 클래스가 포함된 새 코드 파일이 프로젝트에 추가됩니다. 데이터 클래스는 `NorthwindClient.Northwind` 네임스페이스에 만들어집니다.  
  
### <a name="to-access-data-service-data-in-the-wpf-application"></a>WPF 응용 프로그램에서 데이터 서비스 데이터에 액세스하려면  
  
1.  **솔루션 탐색기** 아래 **NorthwindClient**프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **참조 추가**합니다.  
  
2.  참조 추가 대화 상자에서 클릭 된 **.NET** 탭 System.Data.Services.Client.dll 어셈블리를 선택한 다음 클릭 **확인**합니다. **솔루션 탐색기** 아래 **NorthwindClient**을 MainWindow.xaml 파일에 대 한 코드 페이지를 열고 다음 코드를 추가 `using` 문 (`Imports` Visual basic에서).  
  
     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]  
  
3.  해당 데이터 서비스를 쿼리하고 결과를 <xref:System.Data.Services.Client.DataServiceCollection%601>에 바인딩하는 다음 코드를 `MainWindow` 클래스에 삽입합니다.  
  
    > [!NOTE]
    >  Northwind 데이터 서비스 인스턴스를 호스트하는 서버 및 포트로 호스트 이름 `localhost:12345`를 바꾸어야 합니다.  
  
     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]  
  
4.  변경 내용을 저장하는 다음 코드를 `MainWindow` 클래스에 삽입합니다.  
  
     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]  
  
### <a name="to-build-and-run-the-northwindclient-application"></a>NorthwindClient 응용 프로그램을 빌드 및 실행하려면  
  
1.  **솔루션 탐색기**NorthwindClient 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **시작 프로젝트로 설정**합니다.  
  
2.  F5 키를 눌러 응용 프로그램을 시작합니다.  
  
     솔루션이 빌드되고 클라이언트 응용 프로그램이 시작됩니다. 서비스에서 데이터가 요청되고 콘솔에 표시됩니다.  
  
3.  값을 편집는 **수량** 데이터 표 및 클릭 한 다음 열 **저장**합니다.  
  
     변경 내용이 데이터 서비스에 저장됩니다.  
  
    > [!NOTE]
    >  이 버전의 NorthwindClient 응용 프로그램은 엔터티의 추가와 삭제를 지원하지 않습니다.  
  
## <a name="next-steps"></a>다음 단계  
 샘플 Northwind [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 액세스하는 클라이언트 응용 프로그램을 성공적으로 만들었으며 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 퀵 스타트도 완료했습니다. 에 액세스 하는 방법에 대 한 자세한 내용은 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 에서 공급 한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램 참조 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [리소스](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
