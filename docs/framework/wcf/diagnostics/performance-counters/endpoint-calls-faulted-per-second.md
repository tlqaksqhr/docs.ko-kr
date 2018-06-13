---
title: '끝점: Calls Faulted Per Second'
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: 927f5370237b2502899d61f0b8d4bd79c8e00ea8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472546"
---
# <a name="endpoint-calls-faulted-per-second"></a><span data-ttu-id="f5d5f-102">끝점: Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="f5d5f-102">Endpoint: Calls Faulted Per Second</span></span>
<span data-ttu-id="f5d5f-103">카운터 이름: Calls Faulted Per Second</span><span class="sxs-lookup"><span data-stu-id="f5d5f-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f5d5f-104">설명</span><span class="sxs-lookup"><span data-stu-id="f5d5f-104">Description</span></span>  
 <span data-ttu-id="f5d5f-105">이 끝점에 오류를 반환한 초당 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f5d5f-105">Number of calls that have returned faults to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="f5d5f-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5d5f-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="f5d5f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="f5d5f-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="f5d5f-108">Windows Communication Foundation (WCF) 응용 프로그램에서 서비스 메서드는 SOAP 오류 메시지를 사용 하 여 처리 오류 정보를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5d5f-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="f5d5f-109">SOAP 오류는 서비스 작업의 메타데이터에 포함된 메시지 유형이므로 클라이언트가 실행을 더욱 견고하게 만들거나 대화형으로 만드는 데 사용할 수 있는 오류 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f5d5f-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="f5d5f-110">SOAP 오류는 XML 형식으로 클라이언트에 표현되므로 상호 운용성이 매우 높습니다.</span><span class="sxs-lookup"><span data-stu-id="f5d5f-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5d5f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5d5f-111">See Also</span></span>  
 [<span data-ttu-id="f5d5f-112">계약 및 서비스에서 오류 지정 및 처리</span><span class="sxs-lookup"><span data-stu-id="f5d5f-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
