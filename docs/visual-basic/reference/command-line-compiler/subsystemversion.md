---
title: "/subsystemversion (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: efeade3fcde18f02b3a760adc50d3555df6c9ed7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="subsystemversion-visual-basic"></a><span data-ttu-id="ebe1a-102">/subsystemversion(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebe1a-102">/subsystemversion (Visual Basic)</span></span>
<span data-ttu-id="ebe1a-103">실행 파일이 실행 될 수 있는 Windows 버전을 결정 하는, 생성된 된 실행 파일이 실행 될 수 있는 하위의 최소 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="ebe1a-104">가장 일반적으로이 옵션 하면 실행 파일의 이전 버전의 Windows에 사용할 수 없는 특정 보안 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ebe1a-105">사용 하 여 자체 하위 시스템을 지정 하려면는 [/대상](../../../csharp/language-reference/compiler-options/target-compiler-option.md) 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-105">To specify the subsystem itself, use the [/target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe1a-106">구문</span><span class="sxs-lookup"><span data-stu-id="ebe1a-106">Syntax</span></span>  
  
```vb  
/subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ebe1a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ebe1a-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="ebe1a-108">필요한 최소 버전, 하위 시스템의 주 버전과 부 버전에 대 한 점 표기법에 표현 된 대로입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="ebe1a-109">예를 들어 응용 프로그램 보다 오래 된 Windows 7 6.01, 하려면이 옵션의 값을 설정 하는 경우이 항목의 뒷부분에 나오는 표의 설명에 따라 운영 체제에서 실행할 수 없음을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="ebe1a-110">에 대 한 값을 지정 해야 `major` 및 `minor` 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="ebe1a-111">값은 앞에 오는&0;는 `minor` 버전에는 버전은 변경 되지 않지만 후행&0;입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="ebe1a-112">예를 들어 6.1 및 6.01 동일한 버전을 참조 하지만 6.10은 서로 다른 버전을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="ebe1a-113">혼동을 피하기 위해 두 자리로 부 버전을 표현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebe1a-114">설명</span><span class="sxs-lookup"><span data-stu-id="ebe1a-114">Remarks</span></span>  
 <span data-ttu-id="ebe1a-115">다음 표에서 일반적인 하위 시스템 버전의 Windows 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="ebe1a-116">Windows 버전</span><span class="sxs-lookup"><span data-stu-id="ebe1a-116">Windows version</span></span>|<span data-ttu-id="ebe1a-117">하위 시스템 버전</span><span class="sxs-lookup"><span data-stu-id="ebe1a-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="ebe1a-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="ebe1a-118">Windows 2000</span></span>|<span data-ttu-id="ebe1a-119">5.00</span><span class="sxs-lookup"><span data-stu-id="ebe1a-119">5.00</span></span>|  
|<span data-ttu-id="ebe1a-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="ebe1a-120">Windows XP</span></span>|<span data-ttu-id="ebe1a-121">5.01</span><span class="sxs-lookup"><span data-stu-id="ebe1a-121">5.01</span></span>|  
|<span data-ttu-id="ebe1a-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="ebe1a-122">Windows Server 2003</span></span>|<span data-ttu-id="ebe1a-123">5.02</span><span class="sxs-lookup"><span data-stu-id="ebe1a-123">5.02</span></span>|  
|<span data-ttu-id="ebe1a-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="ebe1a-124">Windows Vista</span></span>|<span data-ttu-id="ebe1a-125">6.00</span><span class="sxs-lookup"><span data-stu-id="ebe1a-125">6.00</span></span>|  
|<span data-ttu-id="ebe1a-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ebe1a-126">Windows 7</span></span>|<span data-ttu-id="ebe1a-127">6.01</span><span class="sxs-lookup"><span data-stu-id="ebe1a-127">6.01</span></span>|  
|<span data-ttu-id="ebe1a-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="ebe1a-128">Windows Server 2008</span></span>|<span data-ttu-id="ebe1a-129">6.01</span><span class="sxs-lookup"><span data-stu-id="ebe1a-129">6.01</span></span>|  
|[!INCLUDE[win8](../../../csharp/language-reference/compiler-options/includes/win8_md.md)]|<span data-ttu-id="ebe1a-130">6.02</span><span class="sxs-lookup"><span data-stu-id="ebe1a-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="ebe1a-131">기본값</span><span class="sxs-lookup"><span data-stu-id="ebe1a-131">Default values</span></span>  
 <span data-ttu-id="ebe1a-132">기본값은 **/subsystemversion** 컴파일러 옵션은 다음 목록에 조건에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-132">The default value of the **/subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="ebe1a-133">다음 목록에서 모든 컴파일러 옵션이 설정 된 경우 기본값은 6.02:</span><span class="sxs-lookup"><span data-stu-id="ebe1a-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="ebe1a-134">/target: appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="ebe1a-134">/target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="ebe1a-135">/target: winmdobj</span><span class="sxs-lookup"><span data-stu-id="ebe1a-135">/target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="ebe1a-136">/platform:arm</span><span class="sxs-lookup"><span data-stu-id="ebe1a-136">/platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   <span data-ttu-id="ebe1a-137">기본값이 6.00 MSBuild를 사용 하는 경우, 대상으로 하 [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)],이 목록에서 앞에 지정 된 컴파일러 옵션 중 하나를 설정 하지 않은 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="ebe1a-138">기본값이 4.00 앞의 조건이 없는 경우 true입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="ebe1a-139">이 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="ebe1a-139">Setting this option</span></span>  
 <span data-ttu-id="ebe1a-140">설정 하는 **/subsystemversion** 컴파일러 옵션 Visual Studio에서.vbproj 파일을 열 및 값을 지정 해야는 `SubsystemVersion` 는 MSBuild xml 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-140">To set the **/subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="ebe1a-141">Visual Studio IDE에서이 옵션을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="ebe1a-142">자세한 내용은이 항목의 앞부분에 나오는 "기본값"를 참조 하거나 [일반 MSBuild 프로젝트 속성](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties)합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe1a-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="ebe1a-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebe1a-143">See Also</span></span>  
[<span data-ttu-id="ebe1a-144">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="ebe1a-144">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

[<span data-ttu-id="ebe1a-145">MSBuild 속성</span><span class="sxs-lookup"><span data-stu-id="ebe1a-145">MSBuild Properties</span></span>](https://docs.microsoft.com/visualstudio/msbuild/msbuild-properties)

