---
title: "&lt;제거&gt; NameValueSectionHandler 및 DictionarySectionHandler 요소"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27b01120cb279dc23b3b081e35f17addc6d1897d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="7c804-102">\<제거 > NameValueSectionHandler 및 DictionarySectionHandler 요소</span><span class="sxs-lookup"><span data-stu-id="7c804-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="7c804-103">이전에 정의 된 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7c804-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="7c804-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7c804-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7c804-105">&nbsp;&nbsp;[**\<sectionName >**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="7c804-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="7c804-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<제거 >**</span><span class="sxs-lookup"><span data-stu-id="7c804-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7c804-107">구문</span><span class="sxs-lookup"><span data-stu-id="7c804-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="7c804-108">특성</span><span class="sxs-lookup"><span data-stu-id="7c804-108">Attribute</span></span>

|           | <span data-ttu-id="7c804-109">설명</span><span class="sxs-lookup"><span data-stu-id="7c804-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7c804-110">**key**</span><span class="sxs-lookup"><span data-stu-id="7c804-110">**key**</span></span>   | <span data-ttu-id="7c804-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7c804-111">Required attribute.</span></span><br><br><span data-ttu-id="7c804-112">제거 설정의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c804-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7c804-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7c804-113">Parent element</span></span>

| <span data-ttu-id="7c804-114">요소</span><span class="sxs-lookup"><span data-stu-id="7c804-114">Element</span></span> | <span data-ttu-id="7c804-115">설명</span><span class="sxs-lookup"><span data-stu-id="7c804-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="7c804-116">**\<sectionName >** 요소</span><span class="sxs-lookup"><span data-stu-id="7c804-116">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="7c804-117">설정을 사용 하는 사용자 지정 구성 섹션에 대 한 정의 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7c804-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7c804-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7c804-118">Child elements</span></span>

<span data-ttu-id="7c804-119">없음</span><span class="sxs-lookup"><span data-stu-id="7c804-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="7c804-120">설명</span><span class="sxs-lookup"><span data-stu-id="7c804-120">Remarks</span></span>

<span data-ttu-id="7c804-121">사용할 수는  **\<제거 >** 설정을 구성 파일 계층 구조에서 더 높은 수준에서 정의 된 응용 프로그램에서 제거할 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7c804-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="7c804-122">예</span><span class="sxs-lookup"><span data-stu-id="7c804-122">Example</span></span>

<span data-ttu-id="7c804-123">사용 하는 방법을 보여 주는 다음 예제는  **\<제거 >** 컴퓨터 구성 파일에 이전에 정의 된 설정을 제거 하는 응용 프로그램 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7c804-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="7c804-124">다음 컴퓨터 구성 파일 코드 선언 섹션  **\<mySection >** 두 설정이 추가 `key1` 및 `key2`에:</span><span class="sxs-lookup"><span data-stu-id="7c804-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="7c804-125">다음 응용 프로그램 구성 파일 코드 제거는 `key2` 에서 설정  **\<mySection >**:</span><span class="sxs-lookup"><span data-stu-id="7c804-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="7c804-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="7c804-126">Configuration file</span></span>

<span data-ttu-id="7c804-127">이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7c804-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c804-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c804-128">See also</span></span>

[<span data-ttu-id="7c804-129">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7c804-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
