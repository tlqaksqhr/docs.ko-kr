---
title: '&lt;선택을 취소&gt; 요소에 대 한 &lt;configSections&gt;'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 42a44d66a3f70d0572484adf4c8dd946edf2297f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752249"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="d927c-102">\<지우기 > 요소에 대 한 \<configSections ></span><span class="sxs-lookup"><span data-stu-id="d927c-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="d927c-103">이전에 정의 된 모든 섹션과 섹션 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="d927c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d927c-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="d927c-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="d927c-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="d927c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<지우기 >**</span><span class="sxs-lookup"><span data-stu-id="d927c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d927c-107">구문</span><span class="sxs-lookup"><span data-stu-id="d927c-107">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="d927c-108">특성</span><span class="sxs-lookup"><span data-stu-id="d927c-108">Attribute</span></span>

|           | <span data-ttu-id="d927c-109">설명</span><span class="sxs-lookup"><span data-stu-id="d927c-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d927c-110">**name**</span><span class="sxs-lookup"><span data-stu-id="d927c-110">**name**</span></span>  | <span data-ttu-id="d927c-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-111">Required attribute.</span></span><br><br><span data-ttu-id="d927c-112">섹션 또는 제거할 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d927c-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d927c-113">Parent element</span></span>

|     | <span data-ttu-id="d927c-114">설명</span><span class="sxs-lookup"><span data-stu-id="d927c-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d927c-115">**\<configSections >** 요소</span><span class="sxs-lookup"><span data-stu-id="d927c-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="d927c-116">구성 섹션 및 네임 스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-116">Contains configuration section and namespace declarations.</span></span> |

# <a name="child-elements"></a><span data-ttu-id="d927c-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d927c-117">Child elements</span></span>

<span data-ttu-id="d927c-118">없음</span><span class="sxs-lookup"><span data-stu-id="d927c-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="d927c-119">설명</span><span class="sxs-lookup"><span data-stu-id="d927c-119">Remarks</span></span>

<span data-ttu-id="d927c-120">**\<지우기 >** 요소 또는 구성 파일 계층 구조에서 더 높은 수준에서 현재 구성 파일에서 이전 정의 된 응용 프로그램에서 모든 섹션 및 섹션 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-120">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="d927c-121">예제</span><span class="sxs-lookup"><span data-stu-id="d927c-121">Example</span></span>

<span data-ttu-id="d927c-122">이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고 사용 하는 방법을 보여 줍니다.는  **\<지우기 >** 에 이전에 정의 된 섹션을 정리 하는 응용 프로그램 구성 파일의 요소는 컴퓨터 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-122">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="d927c-123">다음 컴퓨터 구성 파일 코드를 두 개의 섹션 선언  **\<sampleSection >** 및  **\<anotherSampleSection >**, 응용 프로그램 전에 읽은입니다 구성 파일:</span><span class="sxs-lookup"><span data-stu-id="d927c-123">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="d927c-124">다음 응용 프로그램 구성 파일 코드는 모든 이전에 선언 된 섹션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-124">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="d927c-125">응용 프로그램에 사용 하거나 컴퓨터 구성 파일에 선언 된 섹션 중 하나에 대 한 설정을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-125">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="d927c-126">하지만 설정을 사용할 수 있습니다  **\<anotherSection >** 후 있기 때문에  **\<선택을 취소 >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-126">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="d927c-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d927c-127">Configuration file</span></span>

<span data-ttu-id="d927c-128">이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="d927c-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d927c-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="d927c-129">See also</span></span>

[<span data-ttu-id="d927c-130">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d927c-130">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
