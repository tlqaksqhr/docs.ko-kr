---
title: "SingleTagSectionHandler에 대 한 사용자 지정 요소"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords: custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ee722c7d5db9d58ab1a91f4b1299912981510af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="bd3a4-102">SingleTagSectionHandler에 대 한 사용자 지정 요소</span><span class="sxs-lookup"><span data-stu-id="bd3a4-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="bd3a4-103">정의한 사용자 지정 구성 섹션에 설정을 정의</span><span class="sxs-lookup"><span data-stu-id="bd3a4-103">Defines settings in a custom configuration section that is defined by a</span></span> <section> <span data-ttu-id="bd3a4-104">사용 하 여 요소는 <xref:System.Configuration.SingleTagSectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a4-104">element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="bd3a4-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="bd3a4-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="bd3a4-106">&nbsp;&nbsp;*\<sectionName >*</span><span class="sxs-lookup"><span data-stu-id="bd3a4-106">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="bd3a4-107">구문</span><span class="sxs-lookup"><span data-stu-id="bd3a4-107">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="bd3a4-108">특성</span><span class="sxs-lookup"><span data-stu-id="bd3a4-108">Attributes</span></span>

<span data-ttu-id="bd3a4-109">사용자 정의 특성 및 특성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a4-109">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="bd3a4-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bd3a4-110">Parent element</span></span>

|     | <span data-ttu-id="bd3a4-111">설명</span><span class="sxs-lookup"><span data-stu-id="bd3a4-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bd3a4-112">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="bd3a4-112">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="bd3a4-113">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a4-113">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="bd3a4-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bd3a4-114">Child elements</span></span>

<span data-ttu-id="bd3a4-115">없음</span><span class="sxs-lookup"><span data-stu-id="bd3a4-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="bd3a4-116">설명</span><span class="sxs-lookup"><span data-stu-id="bd3a4-116">Remarks</span></span>

<span data-ttu-id="bd3a4-117"> **\<sectionName >** 정의한 사용자 지정 요소는 [  **\<섹션 >** ](~/docs/framework/configure-apps/file-schema/section-element.md) 태그는 [  **\<configSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a4-117">The **\<sectionName>** element is a custom element defined by a [**\<section>**](~/docs/framework/configure-apps/file-schema/section-element.md) tag in the [**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="bd3a4-118">구성 시스템 반환는 <xref:System.Collections.IDictionary> 호출 하는 경우 개체 <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a4-118">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="bd3a4-119">예</span><span class="sxs-lookup"><span data-stu-id="bd3a4-119">Example</span></span>

<span data-ttu-id="bd3a4-120">다음 예에서는 라는 사용자 지정 요소 선언  **\<sampleSection >** 읽은 설정을 포함 하는 <xref:System.Configuration.SingleTagSectionHandler> 클래스:</span><span class="sxs-lookup"><span data-stu-id="bd3a4-120">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="bd3a4-121">구성 파일</span><span class="sxs-lookup"><span data-stu-id="bd3a4-121">Configuration file</span></span>

<span data-ttu-id="bd3a4-122">이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a4-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd3a4-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd3a4-123">See also</span></span>

[<span data-ttu-id="bd3a4-124">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="bd3a4-124">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
