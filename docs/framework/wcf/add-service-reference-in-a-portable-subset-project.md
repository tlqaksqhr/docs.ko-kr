---
title: "이식 가능한 하위 집합 프로젝트에 서비스 참조 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ccfe0f-a34b-40ca-8f5e-725fa1b8095e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a4074920d3ca616498c14511bf39763d7d87ed3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="add-service-reference-in-a-portable-subset-project"></a><span data-ttu-id="0960b-102">이식 가능한 하위 집합 프로젝트에 서비스 참조 추가</span><span class="sxs-lookup"><span data-stu-id="0960b-102">Add Service Reference in a Portable Subset Project</span></span>
<span data-ttu-id="0960b-103">이식 가능한 하위 집합 프로젝트는.NET 어셈블리 프로그래머가 하나의 소스 트리를 유지 관리 하 고 여러.NET 구현 (예: 데스크톱, Silverlight, Windows Phone 및 XBOX)을 지원 하면서 시스템을 구축 하를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-103">Portable subset projects enable .NET assembly programmers to maintain a single source tree and build system while still supporting multiple .NET implementations (desktop, Silverlight, Windows Phone, and XBOX).</span></span> <span data-ttu-id="0960b-104">이식 가능한 하위 집합 프로젝트는 모든.NET 구현에 사용할 수 있는.NET framework 어셈블리인.NET 이식 가능한 라이브러리만 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-104">Portable subset projects only reference .NET portable libraries which are a .NET framework assembly that can be used on any .NET implementation.</span></span>  
  
## <a name="add-service-reference-details"></a><span data-ttu-id="0960b-105">서비스 참조 추가 정보</span><span class="sxs-lookup"><span data-stu-id="0960b-105">Add Service Reference Details</span></span>  
 <span data-ttu-id="0960b-106">이식 가능한 하위 집합 프로젝트에 서비스 참조를 추가할 경우 다음 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-106">When adding a service reference in a portable subset project the following restrictions are enforced:</span></span>  
  
1.  <span data-ttu-id="0960b-107"><xref:System.Xml.Serialization.XmlSerializer>의 경우 리터럴 인코딩만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-107">For <xref:System.Xml.Serialization.XmlSerializer>, only literal encodings are allowed.</span></span> <span data-ttu-id="0960b-108">SOAP 인코딩은 가져오기 중 오류를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-108">SOAP encodings generate an error during import.</span></span>  
  
2.  <span data-ttu-id="0960b-109"><xref:System.Runtime.Serialization.DataContractSerializer> 시나리오를 사용하는 서비스의 경우 이식 가능한 하위 집합에서만 재사용 형식을 가져오도록 데이터 계약 서로게이트가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-109">For services that use <xref:System.Runtime.Serialization.DataContractSerializer> scenarios, a data contract surrogate is provided to ensure that reused types come only from the portable subset.</span></span>  
  
3.  <span data-ttu-id="0960b-110">이식 가능한 라이브러리에서 지원되지 않는 바인딩(<xref:System.ServiceModel.BasicHttpBinding>, 트랜잭션 흐름, 신뢰할 수 있는 세션 또는 MTOM 인코딩을 사용하지 않는 <xref:System.ServiceModel.WSHttpBinding>, 그리고 해당 사용자 지정 바인딩을 제외한 모든 바인딩)에 의존하는 끝점은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-110">Endpoints which rely on bindings not supported in portable libraries (all bindings except <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding> without transaction flow, reliable sessions, or MTOM encoding, and equivalent custom bindings) are ignored.</span></span>  
  
4.  <span data-ttu-id="0960b-111">가져오기 전 모든 작업의 모든 메시지 설명에서 메시지 헤더가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-111">Message headers are deleted from all message descriptions in all operations before import.</span></span>  
  
5.  <span data-ttu-id="0960b-112">이식되지 않는 특성인 <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute> 및 <xref:System.ServiceModel.TransactionFlowAttribute>는 생성된 클라이언트 프록시 코드에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-112">Non-portable attributes <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute>, and <xref:System.ServiceModel.TransactionFlowAttribute> are removed from generated client proxy code.</span></span>  
  
6.  <span data-ttu-id="0960b-113">이식되지 않는 속성인 ProtectionLevel, SessionMode, IsInitiating, IsTerminating은 <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute> 및 <xref:System.ServiceModel.FaultContractAttribute>에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-113">Non-portable properties ProtectionLevel, SessionMode, IsInitiating, IsTerminating are removed from <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, and <xref:System.ServiceModel.FaultContractAttribute>.</span></span>  
  
7.  <span data-ttu-id="0960b-114">모든 서비스 작업은 클라이언트 프록시에서 비동기 작업으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-114">All service operations are generated as asynchronous operations on the client proxy.</span></span>  
  
8.  <span data-ttu-id="0960b-115">생성된 클라이언트 생성자 중 이식되지 않는 형식을 사용하는 생성자는 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-115">Generated client constructors which use non-portable types are removed.</span></span>  
  
9. <span data-ttu-id="0960b-116">생성된 클라이언트에 <xref:System.Net.CookieContainer> 인스턴스가 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-116">A <xref:System.Net.CookieContainer> instance is exposed on the generated client.</span></span>  
  
10. <span data-ttu-id="0960b-117">파일 맨 위에는 어셈블리 및 코드 생성기 버전을 식별하는 주석(`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`)이 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-117">A comment is inserted at the top of the file identifying the assembly and version of the code generator:`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`</span></span>  
  
11. <span data-ttu-id="0960b-118"><xref:System.Runtime.Serialization.ISerializable> 인터페이스는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-118">The <xref:System.Runtime.Serialization.ISerializable> interface is not supported.</span></span>  
  
12. <span data-ttu-id="0960b-119">Net.Tcp 및 PollingDuplex 바인딩은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-119">Net.Tcp and PollingDuplex bindings are not supported</span></span>  
  
13. <span data-ttu-id="0960b-120">오류에 대해 언제나 <xref:System.Runtime.Serialization.DataContractSerializer>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-120">The <xref:System.Runtime.Serialization.DataContractSerializer> will always be used for faults.</span></span>  
  
14. <span data-ttu-id="0960b-121">이식 가능한 하위 집합 프로젝트에는 <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A>가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0960b-121"><xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is not supported in portable subset projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0960b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0960b-122">See Also</span></span>  
 [<span data-ttu-id="0960b-123">WCF 클라이언트를 사용하여 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="0960b-123">Accessing Services Using a WCF Client</span></span>](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)  
 <span data-ttu-id="0960b-124">[이식 가능한 클래스 라이브러리](http://msdn.microsoft.com/library/gg597391\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="0960b-124">[Portable Class Library](http://msdn.microsoft.com/library/gg597391\(v=vs.110\))</span></span>
