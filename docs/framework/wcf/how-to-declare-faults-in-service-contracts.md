---
title: '방법: 서비스 계약에 오류 선언'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 142ad26702f0732bc5103e29d5a44bc57ab37625
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500238"
---
# <a name="how-to-declare-faults-in-service-contracts"></a><span data-ttu-id="f00e7-102">방법: 서비스 계약에 오류 선언</span><span class="sxs-lookup"><span data-stu-id="f00e7-102">How to: Declare Faults in Service Contracts</span></span>
<span data-ttu-id="f00e7-103">관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-103">In managed code, exceptions are thrown when error conditions occur.</span></span> <span data-ttu-id="f00e7-104">그러나 Windows Communication Foundation (WCF) 응용 프로그램에서 서비스 계약 지정 오류 정보는 서비스 계약에서 SOAP 오류를 선언 하 여 클라이언트에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-104">In Windows Communication Foundation (WCF) applications, however, service contracts specify what error information is returned to clients by declaring SOAP faults in the service contract.</span></span> <span data-ttu-id="f00e7-105">예외 및 오류 간의 관계의 개요를 참조 하십시오. [지정 및 계약 및 서비스에서 처리 오류](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-105">For an overview of the relationship between exceptions and faults, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
### <a name="create-a-service-contract-that-specifies-a-soap-fault"></a><span data-ttu-id="f00e7-106">SOAP 오류를 지정하는 서비스 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="f00e7-106">Create a service contract that specifies a SOAP fault</span></span>  
  
1.  <span data-ttu-id="f00e7-107">작업을 하나 이상 포함하는 서비스 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-107">Create a service contract that contains at least one operation.</span></span> <span data-ttu-id="f00e7-108">예를 들어 참조 [하는 방법: 서비스 계약 정의](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-108">For an example, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2.  <span data-ttu-id="f00e7-109">클라이언트가 알림을 받을 수 있는 오류 조건을 지정할 수 있는 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-109">Select an operation that can specify an error condition about which clients can expect to be notified.</span></span> <span data-ttu-id="f00e7-110">오류 조건을 클라이언트에 SOAP 오류를 반환 합니다. 양쪽 맞춤을 결정 하려면 참조 [지정 및 계약 및 서비스에서 처리 오류](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-110">To decide which error conditions justify returning SOAP faults to clients, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
3.  <span data-ttu-id="f00e7-111">선택한 작업에 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>를 적용하고 serialize할 수 있는 오류 형식을 생성자에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-111">Apply a <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> to the selected operation and pass a serializable fault type to the constructor.</span></span> <span data-ttu-id="f00e7-112">만들기 및 serializable 형식을 사용 하는 방법에 대 한 세부 정보를 참조 하십시오. [서비스 계약에 데이터 전송 지정](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-112">For details about creating and using serializable types, see [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).</span></span> <span data-ttu-id="f00e7-113">다음 예제에서는 `SampleMethod` 작업으로 인해 `GreetingFault`가 발생하도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-113">The following example shows how to specify that the `SampleMethod` operation can result in a `GreetingFault`.</span></span>  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4.  <span data-ttu-id="f00e7-114">오류 조건을 클라이언트에 전달하는 계약의 모든 작업에 대해 2단계와 3단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-114">Repeat steps 2 and 3 for all operations in the contract that communicate error conditions to clients.</span></span>  
  
## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a><span data-ttu-id="f00e7-115">지정한 SOAP 오류를 반환하는 작업 구현</span><span class="sxs-lookup"><span data-stu-id="f00e7-115">Implementing an Operation to Return a Specified SOAP Fault</span></span>  
 <span data-ttu-id="f00e7-116">앞의 절차와 같이 특정 SOAP 오류를 반환하여 오류 조건을 호출 응용 프로그램에 전달할 수 있도록 작업에서 지정하고 나면 다음 단계로 해당 사양을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-116">Once an operation has specified that a specific SOAP fault can be returned (such as in the preceding procedure) to communicate an error condition to a calling application, the next step is to implement that specification.</span></span>  
  
#### <a name="throw-the-specified-soap-fault-in-the-operation"></a><span data-ttu-id="f00e7-117">작업에서 지정한 SOAP 오류 throw</span><span class="sxs-lookup"><span data-stu-id="f00e7-117">Throw the specified SOAP fault in the operation</span></span>  
  
1.  <span data-ttu-id="f00e7-118"><xref:System.ServiceModel.FaultContractAttribute>에 지정된 오류 조건이 작업에서 발생하면 지정한 SOAP 오류가 형식 매개 변수인 새 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-118">When a <xref:System.ServiceModel.FaultContractAttribute>-specified error condition occurs in an operation, throw a new <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the specified SOAP fault is the type parameter.</span></span> <span data-ttu-id="f00e7-119">다음 예제에서는 앞의 절차와 다음 코드 섹션에 표시된 `GreetingFault`에서 `SampleMethod`를 throw하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-119">The following example shows how to throw the `GreetingFault` in the `SampleMethod` shown in the preceding procedure and in the following Code section.</span></span>  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="f00e7-120">예제</span><span class="sxs-lookup"><span data-stu-id="f00e7-120">Example</span></span>  
 <span data-ttu-id="f00e7-121">다음 코드 예제에서는 `GreetingFault` 작업에 대해 `SampleMethod`를 지정하는 단일 작업 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f00e7-121">The following code example shows an implementation of a single operation that specifies a `GreetingFault` for the `SampleMethod` operation.</span></span>  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f00e7-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f00e7-122">See Also</span></span>  
 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
