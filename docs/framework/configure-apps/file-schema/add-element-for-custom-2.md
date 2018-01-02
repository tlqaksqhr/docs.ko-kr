---
title: "&lt;추가&gt; NameValueSectionHandler 및 DictionarySectionHandler 요소"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e29d0007820bb0218338394fe199e7acfd66344e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="3aab9-102">\<추가 > NameValueSectionHandler 및 DictionarySectionHandler 요소</span><span class="sxs-lookup"><span data-stu-id="3aab9-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="3aab9-103">사용자 지정 응용 프로그램 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3aab9-103">Adds custom application settings.</span></span> <span data-ttu-id="3aab9-104">각  **\<추가 >** 태그는 키/값 쌍을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aab9-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="3aab9-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="3aab9-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="3aab9-106">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="3aab9-106">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="3aab9-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<추가 >**</span><span class="sxs-lookup"><span data-stu-id="3aab9-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="3aab9-108">구문</span><span class="sxs-lookup"><span data-stu-id="3aab9-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="3aab9-109">특성</span><span class="sxs-lookup"><span data-stu-id="3aab9-109">Attributes</span></span>

| <span data-ttu-id="3aab9-110">특성</span><span class="sxs-lookup"><span data-stu-id="3aab9-110">Attribute</span></span> | <span data-ttu-id="3aab9-111">설명</span><span class="sxs-lookup"><span data-stu-id="3aab9-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="3aab9-112">**key**</span><span class="sxs-lookup"><span data-stu-id="3aab9-112">**key**</span></span>   | <span data-ttu-id="3aab9-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3aab9-113">Required attribute.</span></span><br><br><span data-ttu-id="3aab9-114">설정의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3aab9-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="3aab9-115">**value**</span><span class="sxs-lookup"><span data-stu-id="3aab9-115">**value**</span></span> | <span data-ttu-id="3aab9-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3aab9-116">Required attribute.</span></span><br><br><span data-ttu-id="3aab9-117">설정의 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3aab9-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="3aab9-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3aab9-118">Parent element</span></span>

| <span data-ttu-id="3aab9-119">요소</span><span class="sxs-lookup"><span data-stu-id="3aab9-119">Element</span></span> | <span data-ttu-id="3aab9-120">설명</span><span class="sxs-lookup"><span data-stu-id="3aab9-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="3aab9-121">**\<sectionName >** 요소</span><span class="sxs-lookup"><span data-stu-id="3aab9-121">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="3aab9-122">설정을 사용 하는 사용자 지정 구성 섹션에 대 한 정의 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3aab9-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3aab9-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3aab9-123">Child elements</span></span>

<span data-ttu-id="3aab9-124">없음</span><span class="sxs-lookup"><span data-stu-id="3aab9-124">None</span></span>

## <a name="example"></a><span data-ttu-id="3aab9-125">예</span><span class="sxs-lookup"><span data-stu-id="3aab9-125">Example</span></span>

<span data-ttu-id="3aab9-126">사용자 지정 구성 섹션 정의 및 사용 하는 방법을 보여 주는 다음 예제는  **\<추가 >** 요소 섹션으로 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aab9-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="3aab9-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="3aab9-127">Configuration file</span></span>

<span data-ttu-id="3aab9-128">이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3aab9-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="3aab9-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3aab9-129">See also</span></span>

[<span data-ttu-id="3aab9-130">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="3aab9-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
