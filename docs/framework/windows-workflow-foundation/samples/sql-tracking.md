---
title: "SQL 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dcffb306c8466e63e0d5888c91d5f6015845d81c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="sql-tracking"></a>SQL 추적
이 샘플에서는 SQL 데이터베이스에 추적 레코드를 기록하는 사용자 지정 SQL 추적 참가자를 작성하는 방법을 보여 줍니다. [!INCLUDE[wf](../../../../includes/wf-md.md)]에서는 워크플로 인스턴스의 실행을 시각적으로 추적할 수 있는 워크플로를 제공합니다. 추적 런타임에서는 워크플로를 실행하는 동안 워크플로 추적 레코드를 내보냅니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]워크플로 추적을 참조 하세요. [워크플로 추적 및 트레이싱](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  SQL Server 2008 또는 SQL Server 2008 Express 이상 버전이 설치되어 있는지 확인합니다. 샘플과 함께 제공되는 스크립트에서는 로컬 컴퓨터에 SQL Express 인스턴스가 사용되는 것으로 가정합니다. 로컬 컴퓨터에 다른 인스턴스를 사용하고 있으면 샘플을 실행하기 전에 데이터베이스 관련 스크립트를 수정해야 합니다.  
  
2.  스크립트 디렉터리(\WF\Basic\Tracking\SqlTracking\CS\Scripts)에서 Trackingsetup.cmd를 실행하여 SQL Server 추적 데이터베이스를 만듭니다. 이렇게 하면 TrackingSample이라는 데이터베이스가 생성됩니다.  
  
    > [!NOTE]
    >  이 스크립트에서는 SQL Express의 기본 인스턴스를 기반으로 데이터베이스를 만듭니다. 다른 데이터베이스 인스턴스를 기반으로 이를 설치하려면 Trackingsetup.cmd 스크립트를 편집합니다.  
  
3.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 SqlTrackingSample.sln을 엽니다.  
  
4.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
5.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
     브라우저 창이 열리고 응용 프로그램의 디렉터리 목록이 표시됩니다.  
  
6.  브라우저에서 StockPriceService.xamlx를 클릭합니다.  
  
7.  브라우저에 StockPriceService 페이지가 표시됩니다. 이 페이지에는 로컬 서비스 WSDL 주소가 포함되어 있습니다. 이 주소를 복사합니다.  
  
     로컬 서비스 WSDL 주소 예로는 http://localhost:65193/StockPriceService.xamlx?wsdl이 있습니다.  
  
8.  [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 WCF 테스트 클라이언트(WcfTestClient.exe)를 실행합니다. 이는 Microsoft Visual Studio 10.0\Common7\IDE 디렉터리에 있습니다.  
  
9. WCF 테스트 클라이언트에서 클릭는 **파일** 메뉴와 선택 **서비스 추가**합니다. 로컬 서비스 주소를 텍스트 상자에 붙여넣습니다. 클릭 **확인** 는 대화 상자를 닫습니다.  
  
10. WCF 테스트 클라이언트에서 두 번 클릭 **GetStockPrice**합니다. 열립니다는 `GetStockPrice` 값을 입력 한 매개 변수를 사용 하는 작업 `Contoso` 클릭 **Invoke**합니다.  
  
11. 내보낸 추적 레코드가 SQL 데이터베이스에 기록됩니다. 추적 레코드를 보려면 SQL Management Studio에서 TrackingSample 데이터베이스를 열고 테이블을 찾습니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]SQL Server Management Studio 참조 [SQL Server Management Studio 소개](http://go.microsoft.com/fwlink/?LinkId=165645)합니다. SQL Server 2008 Management Studio Express를 다운로드할 수 있습니다 [여기](http://go.microsoft.com/fwlink/?LinkId=180520)합니다. 테이블에 대해 선택 쿼리를 실행하면 해당 테이블에 저장되어 있는 추적 레코드 내의 데이터가 표시됩니다.  
  
#### <a name="to-uninstall-the-sample"></a>샘플을 제거하려면  
  
1.  샘플 디렉터리(\WF\Basic\Tracking\SqlTracking)에서 Trackingcleanup.cmd 스크립트를 실행합니다.  
  
    > [!NOTE]
    >  Trackingcleanup.cmd가 로컬 컴퓨터 SQL Express에서 데이터베이스를 삭제하려고 시도합니다. 다른 SQL Server 인스턴스를 사용하는 경우 Trackingcleanup.cmd를 편집합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)
