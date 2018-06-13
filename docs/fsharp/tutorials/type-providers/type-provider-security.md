---
title: 형식 공급자 보안
description: '형식 공급자에 대 한 트러스트 설정을 변경 하는 방법을 포함 하 여 F # 형식 공급자 보안에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 66a873a32029d706f1f6fab50dd4f93bc29bca03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563547"
---
# <a name="type-provider-security"></a><span data-ttu-id="aedc1-103">형식 공급자 보안</span><span class="sxs-lookup"><span data-stu-id="aedc1-103">Type Provider Security</span></span>

<span data-ttu-id="aedc1-104">형식 공급자는 (Dll) F # 프로젝트 또는 스크립트에서 참조 하는 어셈블리 외부 데이터 원본에 연결 하 고 F # 형식 환경에이 형식 정보를 노출 하는 코드가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-104">Type providers are assemblies (DLLs) referenced by your F# project or script that contain code to connect to external data sources and surface this type information to the F# type environment.</span></span> <span data-ttu-id="aedc1-105">일반적으로 참조 된 어셈블리의 코드에서에서 컴파일 및 다음 코드를 실행 (또는 스크립트의 경우 코드는 F # Interactive로 보내기) 하는 경우에 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-105">Typically, code in referenced assemblies is only run when you compile and then execute the code (or in the case of a script, send the code to F# Interactive).</span></span> <span data-ttu-id="aedc1-106">그러나 형식 공급자 어셈블리의 코드 편집기에서 단순히 찾아볼 때 Visual Studio 내 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-106">However, a type provider assembly will run inside Visual Studio when the code is merely browsed in the editor.</span></span> <span data-ttu-id="aedc1-107">이 형식 공급자 등 및 요약 정보 도구 설명, IntelliSense 완성 등 편집기에 추가 정보를 추가 하기 위해 실행 해야 하기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-107">This happens because type providers need to run to add extra information to the editor, such as Quick Info tooltips, IntelliSense completions, and so on.</span></span> <span data-ttu-id="aedc1-108">결과적으로, 추가 보안 고려 사항이 형식에 대 한 공급자 어셈블리를 Visual Studio 프로세스 내부에 자동으로 실행 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-108">As a result, there are extra security considerations for type provider assemblies, since they run automatically inside the Visual Studio process.</span></span>


## <a name="security-warning-dialog"></a><span data-ttu-id="aedc1-109">보안 경고 대화 상자</span><span class="sxs-lookup"><span data-stu-id="aedc1-109">Security Warning Dialog</span></span>
<span data-ttu-id="aedc1-110">특정 형식 공급자 어셈블리를 사용 하 여 처음으로, Visual Studio 형식 공급자가 실행 되려고 함을 경고 하는 보안 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-110">When using a particular type provider assembly for the first time, Visual Studio displays a security dialog that warns you that the type provider is about to run.</span></span> <span data-ttu-id="aedc1-111">Visual Studio에서 형식 공급자를 로드 하기 전에이 특정 공급자를 신뢰 하는 경우 수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-111">Before Visual Studio loads the type provider, it gives you the opportunity to decide if you trust this particular provider.</span></span> <span data-ttu-id="aedc1-112">""형식 공급자의 소스를 신뢰 하는 경우 다음 I 트러스트 선택이 형식 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-112">If you trust the source of the type provider, then select "I trust this type provider."</span></span> <span data-ttu-id="aedc1-113">형식 공급자의 소스를 신뢰 하지 않는 경우 다음 선택 "I" 신뢰 하지 않습니다이 형식 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-113">If you do not trust the source of the type provider, then select "I do not trust this type provider."</span></span> <span data-ttu-id="aedc1-114">공급자를 신뢰를 사용 하면 Visual Studio 내에서 실행 하 고 IntelliSense를 제공 하 고 기능을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-114">Trusting the provider enables it to run inside Visual Studio and provide IntelliSense and build features.</span></span> <span data-ttu-id="aedc1-115">하지만 악성 자체 형식 공급자 인 경우 해당 코드 실행을 손상 시킬 수 컴퓨터.</span><span class="sxs-lookup"><span data-stu-id="aedc1-115">But if the type provider itself is malicious, running its code could compromise your machine.</span></span>

<span data-ttu-id="aedc1-116">프로젝트가 형식 공급자를 신뢰 하지 대화 상자에서 선택한를 참조 하는 코드를 포함 하는 경우 다음 컴파일 타임에 경우 컴파일러는 보고 형식 공급자를 신뢰할 수 있는지 여부를 나타내는 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-116">If your project contains code that references type providers that you chose in the dialog not to trust, then at compile time, the compiler will report an error that indicates that the type provider is untrusted.</span></span> <span data-ttu-id="aedc1-117">신뢰할 수 없는 형식 공급자에 의존 하는 모든 형식은 빨간색 물결선으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-117">Any types that are dependent on the untrusted type provider are indicated by red squiggles.</span></span> <span data-ttu-id="aedc1-118">편집기에서 코드를 찾아보려면 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-118">It is safe to browse the code in the editor.</span></span>

<span data-ttu-id="aedc1-119">Visual Studio에서 직접 신뢰 설정을 변경 하려는 경우 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-119">If you decide to change the trust setting directly in Visual Studio, perform the following steps.</span></span>


#### <a name="to-change-the-trust-settings-for-type-providers"></a><span data-ttu-id="aedc1-120">형식 공급자에 대 한 트러스트 설정을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="aedc1-120">To change the trust settings for type providers</span></span>

1. <span data-ttu-id="aedc1-121">에 `Tools` 메뉴 선택 `Options`, 확장의 `F# Tools` 노드.</span><span class="sxs-lookup"><span data-stu-id="aedc1-121">On the `Tools` menu, select `Options`, and expand the `F# Tools` node.</span></span>
<br />

2. <span data-ttu-id="aedc1-122">선택 `Type Providers`, 형식 공급자의 목록에서 신뢰 하는 형식 공급자에 대 한 확인란을 선택 하 고 신뢰 하지 않는 것에 대 한 확인란의 선택을 취소 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aedc1-122">Select `Type Providers`, and in the list of type providers, select the check box for type providers you trust, and clear the check box for those you don't trust.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="aedc1-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aedc1-123">See Also</span></span>
[<span data-ttu-id="aedc1-124">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="aedc1-124">Type Providers</span></span>](index.md)
