---
title: '&lt;httpWebRequest&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1d1dce38e5188824ba1412d3f2a285bd2304f147
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741970"
---
# <a name="lthttpwebrequestgt-element-network-settings"></a><span data-ttu-id="d0220-102">&lt;httpWebRequest&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="d0220-102">&lt;httpWebRequest&gt; Element (Network Settings)</span></span>
<span data-ttu-id="d0220-103">웹 요청 매개 변수를 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="d0220-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d0220-104">\<configuration></span></span>  
<span data-ttu-id="d0220-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="d0220-105">\<system.net></span></span>  
<span data-ttu-id="d0220-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="d0220-106">\<settings></span></span>  
<span data-ttu-id="d0220-107">\<httpWebRequest ></span><span class="sxs-lookup"><span data-stu-id="d0220-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0220-108">구문</span><span class="sxs-lookup"><span data-stu-id="d0220-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0220-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d0220-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d0220-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0220-111">특성</span><span class="sxs-lookup"><span data-stu-id="d0220-111">Attributes</span></span>  
  
|<span data-ttu-id="d0220-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="d0220-112">**Attribute**</span></span>|<span data-ttu-id="d0220-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="d0220-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="d0220-114">킬로바이트 단위로, 응답 헤더의 최대 길이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="d0220-115">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-115">The default is 64.</span></span> <span data-ttu-id="d0220-116">값이-1 크기 제한이 없음을 응답 헤더에 적용 됩니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="d0220-117">킬로바이트 단위로 오류 응답의 최대 길이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="d0220-118">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-118">The default is 64.</span></span> <span data-ttu-id="d0220-119">값이-1 크기 제한이 없음을 오류 응답에 적용 됩니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="d0220-120">권한이 없는 오류 코드, 바이트에 대 한 응답으로 업로드의 최대 길이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="d0220-121">기본값은 -1입니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-121">The default is -1.</span></span> <span data-ttu-id="d0220-122">값이-1 크기 제한이 없음을 업로드에 적용 됩니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="d0220-123">안전 하지 않은 헤더를 구문 분석을 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="d0220-124">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0220-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d0220-125">Child Elements</span></span>  
 <span data-ttu-id="d0220-126">없음</span><span class="sxs-lookup"><span data-stu-id="d0220-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0220-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d0220-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d0220-128">**요소**</span><span class="sxs-lookup"><span data-stu-id="d0220-128">**Element**</span></span>|<span data-ttu-id="d0220-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="d0220-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="d0220-130">settings</span><span class="sxs-lookup"><span data-stu-id="d0220-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="d0220-131"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0220-132">설명</span><span class="sxs-lookup"><span data-stu-id="d0220-132">Remarks</span></span>  
 <span data-ttu-id="d0220-133">기본적으로.NET Framework URI 구문 분석에 대 한 RFC 2616 엄격 하 게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="d0220-134">일부 서버 응답 하 게 허용 되지 않는 필드에 제어 문자가 포함 될 수 있습니다는 <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> throw 하는 메서드는 <xref:System.Net.WebException>합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="d0220-135">경우 **useUnsafeHeaderParsing** 로 설정 된 **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> 되지만 경우에 throw 하지 않는 것, 응용 프로그램은 여러 형태의 URI 구문 분석 공격에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="d0220-136">가장 적합 한 솔루션에 대 한 응답 제어 문자가 포함 되지 서버를 변경 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d0220-137">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d0220-137">Configuration Files</span></span>  
 <span data-ttu-id="d0220-138">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0220-139">예제</span><span class="sxs-lookup"><span data-stu-id="d0220-139">Example</span></span>  
 <span data-ttu-id="d0220-140">다음 예제에서는 큰 값을 지정 하는 방법을 보여 줍니다. 일반적인 최대 헤더 길이 보다 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0220-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0220-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0220-141">See Also</span></span>  
 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>  
 [<span data-ttu-id="d0220-142">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d0220-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
