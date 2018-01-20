---
title: "연습으로 학습"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8ae2965-6a49-4155-89b0-7fab2c488ab1
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c49ecfec032a20090e8eca1c94efe9e1f35cce7d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="learning-by-walkthroughs"></a>연습으로 학습
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서에서는 여러 가지 연습을 제공 합니다. 이 항목에서는 몇 가지 일반적인 연습 문제와 해결 방법을 살펴보고 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 배울 수 있는 여러 초급 수준 연습에 대한 링크를 제공합니다.  
  
> [!NOTE]
>  이 시작 단원의 연습에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술을 지원하는 기본 코드가 제공됩니다. 실제 작업에서는 일반적으로 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 및 Windows Forms 프로젝트를 사용하여 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램을 구현합니다. [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] 설명서에는 이러한 목적을 위한 예제와 연습이 포함되어 있습니다.  
  
## <a name="getting-started-walkthroughs"></a>연습 시작  
 이 단원에서는 여러 연습을 사용할 수 있습니다. 이러한 연습은 샘플 Northwind 데이터베이스에 기반을 두며 복잡성을 최소화하여 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기능을 천천히 배울 수 있도록 제공됩니다.  
  
 일반적으로 따라야 하는 단계는 다음과 같습니다.  
  
|목표|Visual Basic|C#|  
|---------------|------------------|---------|  
|엔터티 클래스를 만들고 단순 쿼리를 실행합니다.|[연습: 간단한 개체 모델 및 쿼리(Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md)|[연습: 간단한 개체 모델 및 쿼리(C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md)|  
|두 번째 클래스를 추가하고 좀 더 복잡한 쿼리를 실행합니다.<br /><br /> 이 연습을 수행하려면 이전 연습을 완료해야 합니다.|[연습: 관계 간 쿼리(Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md)|[연습: 관계 간 쿼리(C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md)|  
|데이터베이스에서 항목을 추가, 변경 및 삭제합니다.|[연습: 데이터 조작(Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)|[연습: 데이터 조작(C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)|  
|저장 프로시저를 사용합니다.|[연습: 저장 프로시저만 사용(Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)|[연습: 저장 프로시저만 사용(C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)|  
  
## <a name="general"></a>일반  
 일반적으로 다음과 같은 정보가 이러한 연습과 관련됩니다.  
  
-   환경: 각 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 연습에서는 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 IDE(통합 개발 환경)로 사용합니다.  
  
-   SQL 엔진: 이러한 연습은 SQL Server Express를 사용하여 구현하도록 작성됩니다. SQL Server Express가 없을 경우 무료로 다운로드할 수 있습니다. 자세한 내용은 참조 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 연습에서는 파일 이름을 연결 문자열로 사용합니다. 간단하게 파일 이름으로 지정하는 것은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]이 SQL Server Express 사용자에게 제공하는 편리한 기능으로 항상 보안 문제에 주의해야 합니다. 자세한 내용은 참조 [linq to SQL 보안](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md)합니다.  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 연습을 수행하려면 일반적으로 Northwind 샘플 데이터베이스가 있어야 합니다. 자세한 내용은 참조 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.  
  
-   연습에서 표시되는 대화 상자와 메뉴 명령은 실제 설정이나 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 클릭합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
-   다중 계층 시나리오를 다루는 연습의 경우 서버는 개발 컴퓨터와 별개인 컴퓨터에 있어야 하고 서버에 액세스하기 위한 적절한 권한이 있어야 합니다.  
  
-   일반적으로 Northwind 샘플 데이터베이스의 Orders 테이블을 나타내는 클래스의 이름은 `[Order]`입니다. `Order`가 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]에서 키워드이기 때문에 이스케이프가 필요합니다.  
  
## <a name="troubleshooting"></a>문제 해결  
 이러한 연습에 사용되는 데이터베이스에 액세스하기 위한 충분한 사용 권한이 없기 때문에 런타임 오류가 발생할 수 있습니다. 이와 관련된 가장 일반적인 문제를 해결하는 데 도움이 되는 다음 단계를 참조하세요.  
  
### <a name="log-on-issues"></a>로그온 문제  
 응용 프로그램에서 허용되지 않은 데이터베이스 로그온을 통해 데이터베이스에 액세스를 시도하는 경우에 발생합니다.  
  
##### <a name="to-verify-or-change-the-database-log-on"></a>데이터베이스 로그온을 확인하거나 변경하려면  
  
1.  Windows **시작** 메뉴에서 **모든 프로그램**, **Microsoft SQL Server 2005**, 가리킨 **구성 도구**, 클릭 하 고 **SQL Server 구성 관리자**합니다.  
  
2.  왼쪽된 창에는 **SQL Server 구성 관리자**, 클릭 **SQL Server 2005 서비스**합니다.  
  
3.  오른쪽 창에서 마우스 오른쪽 단추로 클릭 **SQL Server (SQLEXPRESS)**, 클릭 하 고 **속성**합니다.  
  
4.  클릭는 **로그온** 탭 하 고 서버에 로그온 하려는 하는 방법을 확인 합니다.  
  
     대부분의 경우에서 **로컬 시스템** 작동 합니다.  
  
     변경을 수행한 경우 클릭 **다시 시작** 서비스 다시 시작 합니다.  
  
### <a name="protocols"></a>프로토콜  
 데이터베이스에 액세스하기 위한 프로토콜이 응용 프로그램에 대해 올바르게 설정되지 않은 경우가 있습니다. 예를 들어는 **명명 된 파이프** 프로토콜은 연습에 필요한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], 기본적으로 사용 되지 않습니다.  
  
##### <a name="to-enable-the-named-pipes-protocol"></a>명명된 파이프 프로토콜을 사용하도록 설정하려면  
  
1.  왼쪽된 창에는 **SQL Server 구성 관리자**, 확장 **SQL Server 2005 네트워크 구성**, 클릭 하 고 **SQLEXPRESS에 대 한 프로토콜**합니다.  
  
2.  오른쪽 창에 있는지 확인 하는 **명명 된 파이프** 프로토콜을 사용할 수 있습니다. 그렇지 않은 경우 마우스 오른쪽 단추로 클릭 **명명 된 파이프** 클릭 하 고 **사용**합니다.  
  
     서비스를 중지했다가 다시 시작해야 합니다. 다음 블록의 단계를 따릅니다.  
  
### <a name="stopping-and-restarting-the-service"></a>서비스 중지 및 다시 시작  
 변경 내용을 적용하려면 서비스를 중지했다가 다시 시작해야 합니다.  
  
##### <a name="to-stop-and-restart-the-service"></a>서비스를 중지했다가 다시 시작하려면  
  
1.  왼쪽된 창에는 **SQL Server 구성 관리자**, 클릭 **SQL Server 2005 서비스**합니다.  
  
2.  오른쪽 창에서 마우스 오른쪽 단추로 클릭 **SQL Server (SQLEXPRESS)**, 클릭 하 고 **중지**합니다.  
  
3.  마우스 오른쪽 단추로 클릭 **SQL Server (SQLEXPRESS)**, 클릭 하 고 **다시 시작**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
