---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73fad36b5bf14745ca70d297fa988b90d46990df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="7c0ec-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="7c0ec-102">ServiceCredentials</span></span>
<span data-ttu-id="7c0ec-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="7c0ec-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c0ec-104">구문</span><span class="sxs-lookup"><span data-stu-id="7c0ec-104">Syntax</span></span>  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7c0ec-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7c0ec-105">Methods</span></span>  
 <span data-ttu-id="7c0ec-106">ServiceCredentials 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7c0ec-107">속성</span><span class="sxs-lookup"><span data-stu-id="7c0ec-107">Properties</span></span>  
 <span data-ttu-id="7c0ec-108">ServiceCredentials 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="7c0ec-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="7c0ec-109">ClientCertificate</span></span>  
 <span data-ttu-id="7c0ec-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="7c0ec-110">Data type: string</span></span>  
  
 <span data-ttu-id="7c0ec-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7c0ec-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7c0ec-112">이 서비스에 대한 클라이언트 인증서 인증 및 구축 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="7c0ec-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="7c0ec-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="7c0ec-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="7c0ec-114">Data type: string</span></span>  
  
 <span data-ttu-id="7c0ec-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7c0ec-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7c0ec-116">이 서비스에 대해 현재 발급된 토큰 인증 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="7c0ec-117">Peer</span><span class="sxs-lookup"><span data-stu-id="7c0ec-117">Peer</span></span>  
 <span data-ttu-id="7c0ec-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="7c0ec-118">Data type: string</span></span>  
  
 <span data-ttu-id="7c0ec-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7c0ec-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7c0ec-120">피어 전송 끝점이 사용하는 현재 자격 증명 인증 및 구축 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="7c0ec-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="7c0ec-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="7c0ec-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="7c0ec-122">Data type: string</span></span>  
  
 <span data-ttu-id="7c0ec-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7c0ec-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7c0ec-124">현재 보안 대화 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="7c0ec-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="7c0ec-125">ServiceCertificate</span></span>  
 <span data-ttu-id="7c0ec-126">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="7c0ec-126">Data type: string</span></span>  
  
 <span data-ttu-id="7c0ec-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7c0ec-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7c0ec-128">이 서비스와 연관된 인증서입니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="7c0ec-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="7c0ec-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="7c0ec-130">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="7c0ec-130">Data type: string</span></span>  
  
 <span data-ttu-id="7c0ec-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7c0ec-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7c0ec-132">이 서비스에 대한 사용자 이름/암호 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="7c0ec-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="7c0ec-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="7c0ec-134">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="7c0ec-134">Data type: string</span></span>  
  
 <span data-ttu-id="7c0ec-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="7c0ec-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7c0ec-136">이 서비스에 대한 Windows 인증 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c0ec-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7c0ec-137">Requirements</span></span>  
  
|<span data-ttu-id="7c0ec-138">MOF</span><span class="sxs-lookup"><span data-stu-id="7c0ec-138">MOF</span></span>|<span data-ttu-id="7c0ec-139">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7c0ec-140">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7c0ec-140">Namespace</span></span>|<span data-ttu-id="7c0ec-141">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c0ec-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c0ec-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c0ec-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
