---
title: -/subsystemversion (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9369f87f62bd2f481c543f6cdbb3344ac841193e
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="-subsystemversion-visual-basic"></a><span data-ttu-id="68c77-102">-/subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68c77-102">-subsystemversion (Visual Basic)</span></span>
<span data-ttu-id="68c77-103">생성된 실행 파일을 실행할 수 있는 하위 시스템의 최소 버전을 지정하여 실행 파일을 실행할 수 있는 Windows 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="68c77-104">가장 일반적으로, 이 옵션은 실행 파일이 이전 버전의 Windows에서 사용할 수 없는 특정 보안 기능을 활용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68c77-105">하위 시스템 자체를 지정하려면 [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 컴파일러 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68c77-106">구문</span><span class="sxs-lookup"><span data-stu-id="68c77-106">Syntax</span></span>  
  
```vb  
-subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68c77-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68c77-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="68c77-108">주 버전과 부 버전의 점 표기법으로 표현된 필수 최소 버전의 하위 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="68c77-109">예를 들어 이 항목의 뒷부분에 나오는 표의 설명에 따라 이 옵션의 값을 6.01로 설정하는 경우 Windows 7 이전 운영 체제에서는 응용 프로그램을 실행할 수 없도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="68c77-110">`major` 및 `minor`의 값을 정수로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="68c77-111">`minor` 버전에서 선행 0은 버전을 변경하지 않지만 후행 0은 버전을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="68c77-112">예를 들어 6.1과 6.01은 동일한 버전을 가리키지만 6.10은 다른 버전을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="68c77-113">혼동을 피하기 위해 부 버전을 두 자리로 표현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68c77-114">설명</span><span class="sxs-lookup"><span data-stu-id="68c77-114">Remarks</span></span>  
 <span data-ttu-id="68c77-115">다음 표에는 Windows의 일반적인 하위 시스템 버전이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="68c77-116">Windows 버전</span><span class="sxs-lookup"><span data-stu-id="68c77-116">Windows version</span></span>|<span data-ttu-id="68c77-117">하위 시스템 버전</span><span class="sxs-lookup"><span data-stu-id="68c77-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="68c77-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="68c77-118">Windows 2000</span></span>|<span data-ttu-id="68c77-119">5.00</span><span class="sxs-lookup"><span data-stu-id="68c77-119">5.00</span></span>|  
|<span data-ttu-id="68c77-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="68c77-120">Windows XP</span></span>|<span data-ttu-id="68c77-121">5.01</span><span class="sxs-lookup"><span data-stu-id="68c77-121">5.01</span></span>|  
|<span data-ttu-id="68c77-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="68c77-122">Windows Server 2003</span></span>|<span data-ttu-id="68c77-123">5.02</span><span class="sxs-lookup"><span data-stu-id="68c77-123">5.02</span></span>|  
|<span data-ttu-id="68c77-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="68c77-124">Windows Vista</span></span>|<span data-ttu-id="68c77-125">6.00</span><span class="sxs-lookup"><span data-stu-id="68c77-125">6.00</span></span>|  
|<span data-ttu-id="68c77-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="68c77-126">Windows 7</span></span>|<span data-ttu-id="68c77-127">6.01</span><span class="sxs-lookup"><span data-stu-id="68c77-127">6.01</span></span>|  
|<span data-ttu-id="68c77-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="68c77-128">Windows Server 2008</span></span>|<span data-ttu-id="68c77-129">6.01</span><span class="sxs-lookup"><span data-stu-id="68c77-129">6.01</span></span>|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|<span data-ttu-id="68c77-130">6.02</span><span class="sxs-lookup"><span data-stu-id="68c77-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="68c77-131">기본값</span><span class="sxs-lookup"><span data-stu-id="68c77-131">Default values</span></span>  
 <span data-ttu-id="68c77-132">**-subsystemversion** 컴파일러 옵션의 기본값은 다음 목록의 조건에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-132">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="68c77-133">다음 목록의 컴파일러 옵션이 설정된 경우 기본값은 6.02입니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="68c77-134">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="68c77-134">-target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="68c77-135">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="68c77-135">-target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="68c77-136">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="68c77-136">-platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   <span data-ttu-id="68c77-137">MSBuild를 사용하고 [!INCLUDE[net_v45](~/includes/net-v45-md.md)]를 대상으로 하며, 이 목록의 앞에서 지정된 컴파일러 옵션 중 하나를 설정하지 않은 경우 기본값은 6.00입니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](~/includes/net-v45-md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="68c77-138">앞의 조건이 하나도 true가 아닌 경우 기본값은 4.00입니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="68c77-139">이 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="68c77-139">Setting this option</span></span>  
 <span data-ttu-id="68c77-140">설정 하는 **-subsystemversion** 컴파일러 옵션 Visual Studio에서.vbproj 파일을 열 및 값을 지정 해야 합니다는 `SubsystemVersion` MSBuild XML에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-140">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="68c77-141">Visual Studio IDE에서는 이 옵션을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68c77-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="68c77-142">자세한 내용은 이 항목의 앞부분에 나오는 "기본값"이나 [일반적인 MSBuild 프로젝트 속성](/visualstudio/msbuild/common-msbuild-project-properties)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68c77-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="68c77-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68c77-143">See Also</span></span>  
[<span data-ttu-id="68c77-144">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="68c77-144">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

[<span data-ttu-id="68c77-145">MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="68c77-145">MSBuild Properties</span></span>](/visualstudio/msbuild/msbuild-properties)
