---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4c65eb1689d1411cb9083967b9a29c946b7568b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="4a2a8-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="4a2a8-102">TransactionFlowBindingElement</span></span>
<span data-ttu-id="4a2a8-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="4a2a8-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a2a8-104">구문</span><span class="sxs-lookup"><span data-stu-id="4a2a8-104">Syntax</span></span>  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4a2a8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4a2a8-105">Methods</span></span>  
 <span data-ttu-id="4a2a8-106">TransactionFlowBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a2a8-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4a2a8-107">속성</span><span class="sxs-lookup"><span data-stu-id="4a2a8-107">Properties</span></span>  
 <span data-ttu-id="4a2a8-108">TransactionFlowBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a2a8-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="4a2a8-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="4a2a8-109">IssuedTokens</span></span>  
 <span data-ttu-id="4a2a8-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="4a2a8-110">Data type: string</span></span>  
  
 <span data-ttu-id="4a2a8-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4a2a8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a2a8-112">발급된 보안 토큰 헤더(WS-Trust의 IssuedTokens)의 요구 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4a2a8-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="4a2a8-113">TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="4a2a8-113">TransactionProtocol</span></span>  
 <span data-ttu-id="4a2a8-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="4a2a8-114">Data type: string</span></span>  
  
 <span data-ttu-id="4a2a8-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4a2a8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a2a8-116">서비스에서 트랜잭션을 이동하는 데 사용하는 트랜잭션 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="4a2a8-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="4a2a8-117">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="4a2a8-117">Transactions</span></span>  
 <span data-ttu-id="4a2a8-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4a2a8-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="4a2a8-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4a2a8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4a2a8-120">들어오는 트랜잭션이 지원되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a2a8-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a2a8-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a2a8-121">Requirements</span></span>  
  
|<span data-ttu-id="4a2a8-122">MOF</span><span class="sxs-lookup"><span data-stu-id="4a2a8-122">MOF</span></span>|<span data-ttu-id="4a2a8-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a2a8-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4a2a8-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="4a2a8-124">Namespace</span></span>|<span data-ttu-id="4a2a8-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a2a8-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a2a8-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a2a8-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
