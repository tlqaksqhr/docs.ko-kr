---
title: "NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords: custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9722493ec62952d7cbc07d478687b8495d24f95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="b176c-102">NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소</span><span class="sxs-lookup"><span data-stu-id="b176c-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="b176c-103">설정을 사용 하는 사용자 지정 구성 섹션에 대 한 정의 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="b176c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b176c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="b176c-105">&nbsp;&nbsp;**\<sectionName >**</span><span class="sxs-lookup"><span data-stu-id="b176c-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="b176c-106">특성</span><span class="sxs-lookup"><span data-stu-id="b176c-106">Attributes</span></span>

<span data-ttu-id="b176c-107">없음</span><span class="sxs-lookup"><span data-stu-id="b176c-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="b176c-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b176c-108">Parent element</span></span>

|     | <span data-ttu-id="b176c-109">설명</span><span class="sxs-lookup"><span data-stu-id="b176c-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b176c-110">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="b176c-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="b176c-111">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b176c-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b176c-112">Child elements</span></span>

|     | <span data-ttu-id="b176c-113">설명</span><span class="sxs-lookup"><span data-stu-id="b176c-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="b176c-114">[**\<추가 >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) 에 대 한 <xref:System.Configuration.NameValueSectionHandler> 및<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="b176c-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="b176c-115">사용자 지정 응용 프로그램 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="b176c-116">[**\<제거 >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) 에 대 한 <xref:System.Configuration.NameValueSectionHandler> 및<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="b176c-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> |    <span data-ttu-id="b176c-117">이전에 정의 된 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="b176c-118">[**\<지우기 >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) 에 대 한 <xref:System.Configuration.NameValueSectionHandler> 및<xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="b176c-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="b176c-119">섹션에서 이전에 정의 된 모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b176c-120">설명</span><span class="sxs-lookup"><span data-stu-id="b176c-120">Remarks</span></span>

<span data-ttu-id="b176c-121">**\<sectionName >** 정의한 사용자 지정 요소는  **\<섹션 >** 태그는  **\<configSections >**요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="b176c-122">다음 표에서 각 구성 섹션 처리기에 대 한 반환 ConfigurationSettings.GetConfig 메서드가 개체의 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="b176c-123">구성 섹션 처리기</span><span class="sxs-lookup"><span data-stu-id="b176c-123">Configuration section handler</span></span>                        | <span data-ttu-id="b176c-124">반환 형식</span><span class="sxs-lookup"><span data-stu-id="b176c-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="b176c-125">예제</span><span class="sxs-lookup"><span data-stu-id="b176c-125">Example</span></span>

<span data-ttu-id="b176c-126">다음 예제를 사용 하는 섹션을 선언 하는 방법을 보여 줍니다는 <xref:System.Configuration.DictionarySectionHandler> 및 <xref:System.Configuration.NameValueSectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span> 

<span data-ttu-id="b176c-127">첫 번째 사용자 지정 요소는  **\<dictionarySample >**, 읽은 설정을 포함 하는 <xref:System.Configuration.DictionarySectionHandler> 클래스에 `System.dll` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="b176c-128">두 번째 사용자 지정 요소는  **\<mySection >**, 읽은 설정을 포함 하는 <xref:System.Configuration.NameValueSectionHandler> 클래스에 `System.dll` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="b176c-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b176c-129">Configuration file</span></span>

<span data-ttu-id="b176c-130">이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="b176c-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b176c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b176c-131">See also</span></span>

[<span data-ttu-id="b176c-132">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b176c-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
