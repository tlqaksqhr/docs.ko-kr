## <a name="introduction"></a><span data-ttu-id="fe20c-101">소개</span><span class="sxs-lookup"><span data-stu-id="fe20c-101">Introduction</span></span>
<span data-ttu-id="fe20c-102">대상 다시 지정 변경 내용은 다른 .NET Framework를 대상으로 다시 컴파일되는 앱에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-102">Retargeting changes affect apps that are recompiled to target a different .NET Framework.</span></span> <span data-ttu-id="fe20c-103">다음과 같은 변경 내용이 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-103">They include:</span></span>

* <span data-ttu-id="fe20c-104">디자인 타임 환경의 변경 내용.</span><span class="sxs-lookup"><span data-stu-id="fe20c-104">Changes in the design-time environment.</span></span> <span data-ttu-id="fe20c-105">예를 들어 빌드 도구가 이전 경우와 달리 경고를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-105">For example, build tools may emit warnings when previously they did not.</span></span>

* <span data-ttu-id="fe20c-106">런타임 환경의 변경 내용.</span><span class="sxs-lookup"><span data-stu-id="fe20c-106">Changes in the runtime environment.</span></span> <span data-ttu-id="fe20c-107">이 변경 내용은 구체적으로 대상이 변경된 .NET Framework를 대상으로 하는 앱에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-107">These affect only apps that specifically target the retargeted .NET Framework.</span></span> <span data-ttu-id="fe20c-108">이전 버전의 .NET Framework를 대상으로 하는 앱은 예전 그대로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-108">Apps that target previous versions of the .NET Framework behave as they did when running under those versions.</span></span>

<span data-ttu-id="fe20c-109">대상 다시 지정 변경 내용을 설명하는 토픽에서는 개별 변경 내용이 다음과 같은 영향력별로 분류되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-109">In the topics that describe retargeting changes, we have classified individual items by their expected impact, as follows:</span></span>

<span data-ttu-id="fe20c-110">**주 버전** 다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-110">**Major** This is a significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="fe20c-111">**부 버전** 소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-111">**Minor** This is a change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="fe20c-112">**에지 사례** 일반적이지 않은 매우 특별한 시나리오의 앱에 영향을 주는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-112">**Edge case** This is a change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="fe20c-113">**투명** 앱 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-113">**Transparent** This is a change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="fe20c-114">이 변경 내용으로 인한 앱 수정은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe20c-114">The app should not require modification because of this change.</span></span>
