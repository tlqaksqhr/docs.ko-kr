---
title: '&lt;섹션&gt; 요소'
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 17b44ca93efc26f4732f5fe2926f894257d8f984
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746438"
---
# <a name="section-element"></a><span data-ttu-id="6b09a-102">\<섹션 > 요소</span><span class="sxs-lookup"><span data-stu-id="6b09a-102">\<section> element</span></span>

<span data-ttu-id="6b09a-103">구성 섹션 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="6b09a-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6b09a-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6b09a-105">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6b09a-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="6b09a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<섹션 >**</span><span class="sxs-lookup"><span data-stu-id="6b09a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="6b09a-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="6b09a-107">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="6b09a-108">&nbsp;&nbsp;[**\<configSections >**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="6b09a-108">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="6b09a-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup >**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="6b09a-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="6b09a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<섹션 >**</span><span class="sxs-lookup"><span data-stu-id="6b09a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6b09a-111">구문</span><span class="sxs-lookup"><span data-stu-id="6b09a-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="6b09a-112">필수 특성</span><span class="sxs-lookup"><span data-stu-id="6b09a-112">Required attributes</span></span>

|           | <span data-ttu-id="6b09a-113">설명</span><span class="sxs-lookup"><span data-stu-id="6b09a-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6b09a-114">**name**</span><span class="sxs-lookup"><span data-stu-id="6b09a-114">**name**</span></span>  | <span data-ttu-id="6b09a-115">구성 섹션의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="6b09a-116">**type**</span><span class="sxs-lookup"><span data-stu-id="6b09a-116">**type**</span></span>  | <span data-ttu-id="6b09a-117">구성 파일에서 섹션을 읽을 수 있는 구성 섹션 처리기 클래스의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="6b09a-118">형식 값에 "fully-qualified-section-handler-class-name 단순 어셈블리 이름" 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="6b09a-119">단순 어셈블리 이름은의 루트 이름 없이 *.dll* 파일 확장명입니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="6b09a-120">선택적 특성</span><span class="sxs-lookup"><span data-stu-id="6b09a-120">Optional attributes</span></span>

<span data-ttu-id="6b09a-121">다음 특성은 ASP.NET 응용 프로그램에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="6b09a-122">구성 시스템의 다른 응용 프로그램 종류에 대 한 이러한 특성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="6b09a-123">설명</span><span class="sxs-lookup"><span data-stu-id="6b09a-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="6b09a-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="6b09a-124">**allowDefinition**</span></span> | <span data-ttu-id="6b09a-125">섹션에서 사용할 수 있는 구성 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="6b09a-126">다음 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-126">Use one of the following values:</span></span><br><br><span data-ttu-id="6b09a-127">**모든 범위**</span><span class="sxs-lookup"><span data-stu-id="6b09a-127">**Everywhere**</span></span><br><span data-ttu-id="6b09a-128">섹션을을 모든 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="6b09a-129">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-129">This is the default.</span></span><br><span data-ttu-id="6b09a-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="6b09a-130">**MachineOnly**</span></span><br><span data-ttu-id="6b09a-131">섹션을 컴퓨터 구성 파일에만 사용할 수 있습니다 (*Machine.config*).</span><span class="sxs-lookup"><span data-stu-id="6b09a-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="6b09a-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="6b09a-132">**MachineToApplication**</span></span><br><span data-ttu-id="6b09a-133">섹션을을 컴퓨터 구성 파일 또는 응용 프로그램 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="6b09a-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="6b09a-134">**allowLocation**</span></span>   | <span data-ttu-id="6b09a-135">섹션 내에서 사용할 수 있는지 여부를 결정 하는  **\<위치 >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="6b09a-136">다음 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-136">Use one of the following values:</span></span><br><br><span data-ttu-id="6b09a-137">**true**</span><span class="sxs-lookup"><span data-stu-id="6b09a-137">**true**</span></span><br><span data-ttu-id="6b09a-138">섹션 내에서 사용할 수 있습니다는  **\<위치 >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="6b09a-139">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-139">This is the default.</span></span><br><span data-ttu-id="6b09a-140">**false**</span><span class="sxs-lookup"><span data-stu-id="6b09a-140">**false**</span></span><br><span data-ttu-id="6b09a-141">섹션 내에서 사용 되도록 허용 하지 않습니다는  **\<위치 >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="6b09a-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6b09a-142">Parent elements</span></span>

|     | <span data-ttu-id="6b09a-143">설명</span><span class="sxs-lookup"><span data-stu-id="6b09a-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6b09a-144">**\<configSections >** 요소</span><span class="sxs-lookup"><span data-stu-id="6b09a-144">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="6b09a-145">구성 섹션 및 네임 스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="6b09a-146">**\<sectionGroup >** 요소</span><span class="sxs-lookup"><span data-stu-id="6b09a-146">**\<sectionGroup>** Element</span></span>](~/docs/framework/configure-apps/file-schema/sectiongroup-element-for-configsections.md) | <span data-ttu-id="6b09a-147">구성 섹션에 대 한 네임 스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="6b09a-148">A  **\<섹션 >** 요소 중 하나의 자식 요소인  **\<configSections >** 또는  **\<sectionGroup >** 하지 않고 둘 다 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="6b09a-149">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6b09a-149">Child elements</span></span>

<span data-ttu-id="6b09a-150">없음</span><span class="sxs-lookup"><span data-stu-id="6b09a-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="6b09a-151">설명</span><span class="sxs-lookup"><span data-stu-id="6b09a-151">Remarks</span></span>

<span data-ttu-id="6b09a-152">구성 파일에 대 한 새 요소를 정의 구성 섹션을 기본적으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="6b09a-153">새 요소는 구성 섹션 처리기 하는 설정이 포함 되어 (즉, 구현 하는 클래스는 <xref:System.Configuration.IConfigurationSectionHandler> 인터페이스)를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="6b09a-154">특성 및 자식 요소 정의 하는 섹션의 설정을 읽는 데 사용 하는 섹션 처리기에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="6b09a-155">선언에 구성 섹션 처리기는 *Machine.config* 파일을 사용 하면 해당 컴퓨터에서 모든 응용 프로그램 구성 파일에서 구성 섹션을 사용할 수 있는 경우가 아니면는 **allowDefinition**특성 그렇지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="6b09a-156">예제</span><span class="sxs-lookup"><span data-stu-id="6b09a-156">Example</span></span>

<span data-ttu-id="6b09a-157">다음 예제에서는 구성 섹션을 정의 하 고 해당 섹션에 대 한 설정을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="6b09a-158">구성 파일</span><span class="sxs-lookup"><span data-stu-id="6b09a-158">Configuration file</span></span>

<span data-ttu-id="6b09a-159">이 요소는 응용 프로그램 구성 파일을 컴퓨터 구성 파일에 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6b09a-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b09a-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="6b09a-160">See also</span></span>

[<span data-ttu-id="6b09a-161">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="6b09a-161">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
