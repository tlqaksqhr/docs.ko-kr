---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06c0ff11752ae1030e574182cfb825fb87ddc8c7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="3b6e4-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3b6e4-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="3b6e4-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3b6e4-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b6e4-104">구문</span><span class="sxs-lookup"><span data-stu-id="3b6e4-104">Syntax</span></span>  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3b6e4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3b6e4-105">Methods</span></span>  
 <span data-ttu-id="3b6e4-106">XmlDictionaryReaderQuotas 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3b6e4-107">속성</span><span class="sxs-lookup"><span data-stu-id="3b6e4-107">Properties</span></span>  
 <span data-ttu-id="3b6e4-108">XmlDictionaryReaderQuotas 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="3b6e4-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="3b6e4-109">MaxArrayLength</span></span>  
 <span data-ttu-id="3b6e4-110">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="3b6e4-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="3b6e4-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3b6e4-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3b6e4-112">허용된 최대 배열 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="3b6e4-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="3b6e4-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="3b6e4-114">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="3b6e4-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="3b6e4-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3b6e4-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3b6e4-116">각 읽기에 대해 반환되는 최대 허용 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="3b6e4-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="3b6e4-117">MaxDepth</span></span>  
 <span data-ttu-id="3b6e4-118">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="3b6e4-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="3b6e4-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3b6e4-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3b6e4-120">각 읽기에 대한 최대 중첩 노드 깊이입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="3b6e4-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="3b6e4-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="3b6e4-122">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="3b6e4-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="3b6e4-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3b6e4-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3b6e4-124">표 이름에 허용된 최대 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="3b6e4-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="3b6e4-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="3b6e4-126">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="3b6e4-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="3b6e4-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="3b6e4-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3b6e4-128">XML 요소 콘텐츠에 허용되는 최대 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b6e4-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b6e4-129">Requirements</span></span>  
  
|<span data-ttu-id="3b6e4-130">MOF</span><span class="sxs-lookup"><span data-stu-id="3b6e4-130">MOF</span></span>|<span data-ttu-id="3b6e4-131">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3b6e4-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="3b6e4-132">Namespace</span></span>|<span data-ttu-id="3b6e4-133">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b6e4-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b6e4-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b6e4-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
