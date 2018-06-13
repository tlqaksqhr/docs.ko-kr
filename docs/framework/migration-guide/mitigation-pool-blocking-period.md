---
title: '완화: 풀 차단 기간'
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e402ba9cb5de8e85ce6912e2e5b760ef340c2cf4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389956"
---
# <a name="mitigation-pool-blocking-period"></a><span data-ttu-id="f949f-102">완화: 풀 차단 기간</span><span class="sxs-lookup"><span data-stu-id="f949f-102">Mitigation: Pool Blocking Period</span></span>
<span data-ttu-id="f949f-103">Azure SQL 데이터베이스 연결에 대한 연결 풀 차단 기간이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-103">The connection pool blocking period has been removed for connections to Azure SQL databases.</span></span>  
  
## <a name="additional-description"></a><span data-ttu-id="f949f-104">추가 설명</span><span class="sxs-lookup"><span data-stu-id="f949f-104">Additional description</span></span>  
 <span data-ttu-id="f949f-105">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이전 버전에서 데이터베이스에 연결할 때 응용 프로그램에 일시적인 연결 오류가 발생할 경우, 연결 풀이 오류를 캐시하고 5초에서 1분 동안 다시 throw하기 때문에 연결 시도는 신속하게 다시 시도될 수 없습니다. 자세한 내용은 [SQL Server 연결 풀링(ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f949f-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, when an app encounters a transient connection failure when connecting to a database, the connection attempt cannot be retried quickly, because the connection pool caches the error and re-throws it for 5 seconds to 1 min. For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span> <span data-ttu-id="f949f-106">이 동작은 일반적으로 몇 초 내에 복구되는 일시적인 오류가 자주 발생하는 Azure SQL 데이터베이스에 대한 연결 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-106">This behavior is problematic for connections to Azure SQL databases, which often fail with transient errors that are typically recovered from within a few seconds.</span></span> <span data-ttu-id="f949f-107">연결 풀 차단 기능은 데이터베이스를 사용할 수 있어도 광범위한 기간 동안 응용 프로그램 데이터베이스에 연결할 수 없다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-107">The connection pool blocking feature means that the app cannot connect to the database for an extensive period, even though the database is available.</span></span> <span data-ttu-id="f949f-108">이 동작은 Azure SQL 데이터베이스에 연결하고 몇 초 안에 렌더링해야 하는 웹 응용 프로그램에 대해 특히 문제가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-108">This behavior is particularly problematic for web apps that connect to Azure SQL databases and that need to render within a few seconds.</span></span>  
  
 <span data-ttu-id="f949f-109">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터는 알려진 Azure SQL 데이터베이스(*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de)에 대한 연결 열기 요청의 경우 연결 열기 오류가 캐시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-109">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], for connection open requests to known Azure SQL databases (*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), connection open errors are not cached.</span></span> <span data-ttu-id="f949f-110">다른 모든 연결 시도의 경우 연결 풀 차단 기간이 계속 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-110">For all other connection attempts, the connection pool blocking period continues to be enforced.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="f949f-111">영향</span><span class="sxs-lookup"><span data-stu-id="f949f-111">Impact</span></span>  
 <span data-ttu-id="f949f-112">이 변경은 Azure SQL 데이터베이스에 대한 연결 열기 시도를 즉시 다시 시도하도록 하여 클라우드 지원 응용 프로그램의 성능을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-112">This change allows the connection open attempt to be retried immediately for Azure SQL databases, thereby improving the performance of cloud-enabled apps.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="f949f-113">완화</span><span class="sxs-lookup"><span data-stu-id="f949f-113">Mitigation</span></span>  
 <span data-ttu-id="f949f-114">이 변경으로 인해 문제가 발생하는 앱의 경우 새로운 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> 속성을 설정하여 연결 풀 차단 기간을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-114">For apps that are adversely affected by this change, the connection pool blocking period can be configured by setting the new <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property.</span></span>  <span data-ttu-id="f949f-115">속성의 값은 다음의 세 값 중 하나를 사용할 수 있는 <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> 열거형의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-115">The value of the property is a member of the <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> enumeration that can take either of three values:</span></span>  
  
-   `PoolBlockingPeriod.AlwaysBlock` 
  
-   `PoolBlockingPeriod.Auto`  
  
-   `PoolBlockingPeriod.NeverBlock` 
  
 <span data-ttu-id="f949f-116"><xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> 속성을 `PoolBlockingPeriod.AlwaysBlock`으로 설정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f949f-116">The previous behavior can be restored by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property to `PoolBlockingPeriod.AlwaysBlock`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f949f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f949f-117">See Also</span></span>  
 [<span data-ttu-id="f949f-118">런타임 변경 내용</span><span class="sxs-lookup"><span data-stu-id="f949f-118">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
