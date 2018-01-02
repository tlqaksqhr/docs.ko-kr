---
title: "&lt;configSections&gt; 요소에 대 한 &lt;구성&gt;"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 145a2a5cc23758c9fd2211c2da7fee0bbd736f0f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="ce705-102">\<configSections > 요소에 대 한 \<구성 ></span><span class="sxs-lookup"><span data-stu-id="ce705-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="ce705-103">구성 섹션 및 네임 스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ce705-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="ce705-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="ce705-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="ce705-105">&nbsp;&nbsp;**\<configSections >**</span><span class="sxs-lookup"><span data-stu-id="ce705-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="ce705-106">특성</span><span class="sxs-lookup"><span data-stu-id="ce705-106">Attributes</span></span>

<span data-ttu-id="ce705-107">없음</span><span class="sxs-lookup"><span data-stu-id="ce705-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="ce705-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ce705-108">Parent element</span></span>

|     | <span data-ttu-id="ce705-109">설명</span><span class="sxs-lookup"><span data-stu-id="ce705-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ce705-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="ce705-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="ce705-111">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ce705-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ce705-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ce705-112">Child elements</span></span>

|     | <span data-ttu-id="ce705-113">설명</span><span class="sxs-lookup"><span data-stu-id="ce705-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ce705-114">**\<섹션 >**</span><span class="sxs-lookup"><span data-stu-id="ce705-114">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="ce705-115">구성 섹션 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ce705-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="ce705-116">**\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="ce705-116">**\<sectionGroup>**</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="ce705-117">구성 섹션에 대 한 네임 스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ce705-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="ce705-118">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="ce705-118">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/remove-element-for-configsections.md) | <span data-ttu-id="ce705-119">미리 정의 된 섹션 또는 섹션 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ce705-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="ce705-120">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="ce705-120">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/clear-element-for-configsections.md) | <span data-ttu-id="ce705-121">이전에 정의 된 모든 섹션과 섹션 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ce705-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ce705-122">설명</span><span class="sxs-lookup"><span data-stu-id="ce705-122">Remarks</span></span>

<span data-ttu-id="ce705-123">이 요소가 구성 파일에 포함 된 경우의 첫 번째 자식 요소 여야 합니다는  **\<구성 >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ce705-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="ce705-124">예</span><span class="sxs-lookup"><span data-stu-id="ce705-124">Example</span></span>

<span data-ttu-id="ce705-125">다음 예제에서는 구성 섹션을 정의 하 고 해당 섹션에 대 한 설정을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce705-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="ce705-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="ce705-126">Configuration file</span></span>

<span data-ttu-id="ce705-127">이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ce705-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce705-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce705-128">See also</span></span>

[<span data-ttu-id="ce705-129">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ce705-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
