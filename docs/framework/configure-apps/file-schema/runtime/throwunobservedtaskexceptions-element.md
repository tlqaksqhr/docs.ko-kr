---
title: '&lt;ThrowUnobservedTaskExceptions&gt; 요소'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f72bedbaaf0b15ade7ff6b7b8c3edcdfd3fda6d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a><span data-ttu-id="7bd57-102">&lt;ThrowUnobservedTaskExceptions&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="7bd57-102">&lt;ThrowUnobservedTaskExceptions&gt; Element</span></span>
<span data-ttu-id="7bd57-103">작업 예외가 처리되지 않으면 실행 중인 프로세스를 종료할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="7bd57-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7bd57-104">\<configuration></span></span>  
<span data-ttu-id="7bd57-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="7bd57-105">\<runtime></span></span>  
<span data-ttu-id="7bd57-106">\<ThrowUnobservedTaskExceptions ></span><span class="sxs-lookup"><span data-stu-id="7bd57-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bd57-107">구문</span><span class="sxs-lookup"><span data-stu-id="7bd57-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7bd57-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7bd57-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7bd57-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7bd57-110">특성</span><span class="sxs-lookup"><span data-stu-id="7bd57-110">Attributes</span></span>  
  
|<span data-ttu-id="7bd57-111">특성</span><span class="sxs-lookup"><span data-stu-id="7bd57-111">Attribute</span></span>|<span data-ttu-id="7bd57-112">설명</span><span class="sxs-lookup"><span data-stu-id="7bd57-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7bd57-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7bd57-114">예외 처리 되지 않은 작업 실행 중인 프로세스를 종료 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7bd57-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="7bd57-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="7bd57-116">값</span><span class="sxs-lookup"><span data-stu-id="7bd57-116">Value</span></span>|<span data-ttu-id="7bd57-117">설명</span><span class="sxs-lookup"><span data-stu-id="7bd57-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7bd57-118">처리 되지 않은 작업 예외에 대 한 실행 중인 프로세스를 종료 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="7bd57-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="7bd57-120">처리 되지 않은 작업 예외에 대 한 실행 중인 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7bd57-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7bd57-121">Child Elements</span></span>  
 <span data-ttu-id="7bd57-122">없음</span><span class="sxs-lookup"><span data-stu-id="7bd57-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7bd57-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7bd57-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7bd57-124">요소</span><span class="sxs-lookup"><span data-stu-id="7bd57-124">Element</span></span>|<span data-ttu-id="7bd57-125">설명</span><span class="sxs-lookup"><span data-stu-id="7bd57-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7bd57-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7bd57-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="7bd57-128">설명</span><span class="sxs-lookup"><span data-stu-id="7bd57-128">Remarks</span></span>  
 <span data-ttu-id="7bd57-129">예외와 연결 된 경우는 <xref:System.Threading.Tasks.Task> 지켜지지 않았습니다는 없는 <xref:System.Threading.Tasks.Task.Wait%2A> 부모 작업에 연결 되어 있지 않습니다 및 <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> 속성 작업 예외가 관찰 되지 것으로 간주 됩니다 읽지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="7bd57-130">에 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 만든 사람 경우 기본값는 <xref:System.Threading.Tasks.Task> 는 관찰 되지 않은 예외는 가비지 수집, 종료자 예외를 throw 하 고 프로세스를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="7bd57-131">프로세스의 종료는 가비지 수집 및 종료 시기에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="7bd57-132">작업 기반 비동기 코드를 작성 하 고 개발자가 쉽게 수행할 수 있도록는 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] 관찰 되지 않은 예외에 대 한이 기본 동작을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-132">To make it easier for developers to write asynchronous code based on tasks, the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="7bd57-133">관찰 되지 않은 예외 때문에 발생할 수는 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> 이벤트를 발생 수 있지만 기본적으로 프로세스 종료 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="7bd57-134">대신 예외는 이벤트 처리기에서 예외를 관찰 하는 여부에 관계 없이, 이벤트가 발생 한 후 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="7bd57-135">에 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], 사용할 수 있습니다는 [ \<ThrowUnobservedTaskExceptions > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) 사용할 수 있도록 응용 프로그램 구성 파일에는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 동작 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-135">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], you can use the [\<ThrowUnobservedTaskExceptions> element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in an application configuration file to enable the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="7bd57-136">또한 다음과 같은 방법 중 하나에서 예외 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
-   <span data-ttu-id="7bd57-137">환경 변수를 설정 하 여 `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="7bd57-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
-   <span data-ttu-id="7bd57-138">DWORD 레지스트리 설정 하 여 ThrowUnobservedTaskExceptions 값 = 1에서 찾아를\\합니다. NETFramework 키입니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bd57-139">예제</span><span class="sxs-lookup"><span data-stu-id="7bd57-139">Example</span></span>  
 <span data-ttu-id="7bd57-140">다음 예제에서는 응용 프로그램 구성 파일을 사용 하 여 작업의 예외를 throw를 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="7bd57-141">예제</span><span class="sxs-lookup"><span data-stu-id="7bd57-141">Example</span></span>  
 <span data-ttu-id="7bd57-142">다음 예제에서는 작업에서 관찰 되지 않은 예외가 throw 됩니다는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="7bd57-143">코드가 제대로 작동 하려면 릴리스된 프로그램으로 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bd57-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7bd57-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bd57-144">See Also</span></span>  
 [<span data-ttu-id="7bd57-145">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7bd57-145">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="7bd57-146">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7bd57-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
