---
title: 'Visual Studio에서 F #으로 시작.'
description: 'F # Visual Studio와 함께 사용 하는 방법에 알아봅니다.'
ms.date: 02/13/2017
ms.openlocfilehash: 22fbe8086ec133605e1d9b4b28e524fe2ed8ac28
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2018
ms.locfileid: "34728536"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="f2e60-103">Visual Studio에서 F #으로 시작.</span><span class="sxs-lookup"><span data-stu-id="f2e60-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="f2e60-104">F # 및 Visual F # 도구는 Visual Studio IDE에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>  <span data-ttu-id="f2e60-105">를 시작 하려면 [Visual Studio 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)아직 없는 경우, 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-105">To begin, you should [download Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), if you haven't already.</span></span>  <span data-ttu-id="f2e60-106">이 문서에서는 Visual Studio 2017 Community Edition을 사용 하지만 사용할 수 있습니다 F # 원하는 버전으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-106">This article uses the Visual Studio 2017 Community Edition, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="f2e60-107">F # 설치</span><span class="sxs-lookup"><span data-stu-id="f2e60-107">Installing F#</span></span> #

<span data-ttu-id="f2e60-108">처음으로 Visual Studio를 다운로드 하는 경우 Visual Studio 설치 프로그램을 먼저 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-108">If you're downloading Visual Studio for the first time, it will first install the Visual Studio installer.</span></span>  <span data-ttu-id="f2e60-109">설치 관리자에서 모든 버전의 Visual Studio 2017을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-109">Install any version of Visual Studio 2017 from the installer.</span></span> <span data-ttu-id="f2e60-110">이미 있는 경우 설치를 클릭 하 여 **수정**합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-110">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="f2e60-111">다음 작업의 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-111">You'll next see a list of Workloads.</span></span> <span data-ttu-id="f2e60-112">F #는 다음과 같은 작업 중 하나를 통해 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-112">You can install F# through any of the following workloads:</span></span>

|<span data-ttu-id="f2e60-113">작업</span><span class="sxs-lookup"><span data-stu-id="f2e60-113">Workload</span></span>|<span data-ttu-id="f2e60-114">작업</span><span class="sxs-lookup"><span data-stu-id="f2e60-114">Action</span></span>|
|--------|------|
| <span data-ttu-id="f2e60-115">.NET Core 플랫폼 간 개발</span><span class="sxs-lookup"><span data-stu-id="f2e60-115">.NET Core cross-platform development</span></span> | <span data-ttu-id="f2e60-116">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="f2e60-116">No action - F# is installed by default</span></span> |
| <span data-ttu-id="f2e60-117">ASP.NET 및 웹 개발</span><span class="sxs-lookup"><span data-stu-id="f2e60-117">ASP.NET and web development</span></span> | <span data-ttu-id="f2e60-118">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="f2e60-118">No action - F# is installed by default</span></span> |
| <span data-ttu-id="f2e60-119">Azure 개발</span><span class="sxs-lookup"><span data-stu-id="f2e60-119">Azure development</span></span> | <span data-ttu-id="f2e60-120">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="f2e60-120">No action - F# is installed by default</span></span> |
| <span data-ttu-id="f2e60-121">.NET을 사용한 모바일 개발</span><span class="sxs-lookup"><span data-stu-id="f2e60-121">Mobile development with .NET</span></span> | <span data-ttu-id="f2e60-122">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="f2e60-122">No action - F# is installed by default</span></span> |
| <span data-ttu-id="f2e60-123">데이터 과학 및 분석 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f2e60-123">Data science and analytical applications</span></span> | <span data-ttu-id="f2e60-124">동작 안 함-F #은 기본적으로 설치</span><span class="sxs-lookup"><span data-stu-id="f2e60-124">No action - F# is installed by default</span></span> |
| <span data-ttu-id="f2e60-125">.NET 데스크톱 개발</span><span class="sxs-lookup"><span data-stu-id="f2e60-125">.NET desktop development</span></span> | <span data-ttu-id="f2e60-126">선택 **F # 데스크톱 언어 지원** 오른쪽에서</span><span class="sxs-lookup"><span data-stu-id="f2e60-126">Select **F# desktop language support** from the right-hand side</span></span> |
| <span data-ttu-id="f2e60-127">데이터 저장소 및 처리</span><span class="sxs-lookup"><span data-stu-id="f2e60-127">Data storage and processing</span></span> | <span data-ttu-id="f2e60-128">선택 **F # 데스크톱 언어 지원** 오른쪽에서</span><span class="sxs-lookup"><span data-stu-id="f2e60-128">Select **F# desktop language support** from the right-hand side</span></span> |

<span data-ttu-id="f2e60-129">그런 다음 클릭 **수정** 오른쪽 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-129">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="f2e60-130">그러면 선택한 모든 항목이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-130">This will install everything you have selected.</span></span>  <span data-ttu-id="f2e60-131">클릭 하 여 F # 언어 지원과 함께 Visual Studio 2017을 열고 다음 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-131">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="f2e60-132">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="f2e60-132">Creating a console application</span></span>

<span data-ttu-id="f2e60-133">Visual Studio에서 가장 기본적인 프로젝트 중 하나는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-133">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="f2e60-134">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-134">Here's how to do it.</span></span>  <span data-ttu-id="f2e60-135">Visual Studio를 열면:</span><span class="sxs-lookup"><span data-stu-id="f2e60-135">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="f2e60-136">에 **파일** 메뉴에서 **새로**를 선택한 후 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-136">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="f2e60-137">새로 만들기 대화 상자에서를 아래에서 프로젝트 **템플릿**, 나타납니다 **Visual F #** 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-137">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="f2e60-138">F # 서식 파일을 표시 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-138">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="f2e60-139">선택 **.NET Core 콘솔 앱** 또는 **콘솔 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-139">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="f2e60-140">선택 된 **알겠습니다** F # 프로젝트를 만드는 단추!</span><span class="sxs-lookup"><span data-stu-id="f2e60-140">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="f2e60-141">이제 F # 프로젝트를 솔루션 탐색기에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-141">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="f2e60-142">코드 작성</span><span class="sxs-lookup"><span data-stu-id="f2e60-142">Writing your code</span></span>

<span data-ttu-id="f2e60-143">이제 시작 하겠습니다 먼저 일부 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-143">Let's get started by writing some code first.</span></span>  <span data-ttu-id="f2e60-144">다음 사항을 확인는 `Program.fs` 파일을 연 상태 및 다음 내용에 다음을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-144">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="f2e60-145">이전 코드 예제에서 함수 `square` 라는 입력을 가져와서는 정의 된 `x` 여 스스로 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-145">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="f2e60-146">F #에서 사용 하기 때문에 [형식 유추](../language-reference/type-inference.md), 유형의 `x` 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-146">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="f2e60-147">F # 컴파일러 곱하기 올바른지 종류를 이해 하 고에 형식을 할당 합니다 `x` 정도에 따라 `square` 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-147">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="f2e60-148">위로 가져가면 `square`, 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-148">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="f2e60-149">이 함수의 형식 서명이 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-149">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="f2e60-150">다음과 같이 읽을 수 있습니다: "사각형 이라는 정수를 사용 하는 함수는 x는 정수를 생성 하 고"입니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-150">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="f2e60-151">지정 하는 컴파일러는 `square` 는 `int` 형식 곱하기에서 제네릭 없기 때문에 이것이 지금은- *모든* 형식, 하지만 대신는 제네릭 형식의 폐쇄형 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-151">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="f2e60-152">선택 하는 F # 컴파일러 `int` 이 지점 하지만 메이커가 형식 시그니처 호출 하는 경우 `square` 가 다른 입력 형식, 같은 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-152">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="f2e60-153">다른 함수 `main`, 정의 된으로 데코레이팅되 어는 `EntryPoint` 해당 프로그램 실행 F # 컴파일러에 지시 하는 특성 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-153">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="f2e60-154">다른 동일한 규칙에 따라 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), 여기서이 함수에 전달할 수 있는 명령줄 인수 및 정수 코드가 반환 됩니다 (일반적으로 `0`).</span><span class="sxs-lookup"><span data-stu-id="f2e60-154">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="f2e60-155">이라고 하는이 함수에는 `square` 의 인수와 함께 함수가 `12`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-155">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="f2e60-156">F # 컴파일러에는 다음 형식의 할당 `square` 되도록 `int -> int` (사용 되는 함수, 즉는 `int` 하 고 생성 한 `int`).</span><span class="sxs-lookup"><span data-stu-id="f2e60-156">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="f2e60-157">에 대 한 호출 `printfn` 은 형식 문자열에 지정 하는 것에 해당 하는 매개 변수를 C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용 하 여 형식이 지정 된 인쇄 기능 한 다음 결과 새 줄을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-157">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="f2e60-158">코드 실행</span><span class="sxs-lookup"><span data-stu-id="f2e60-158">Running your code</span></span>

<span data-ttu-id="f2e60-159">코드를 실행 하 고 키를 눌러 결과 확인할 수 있습니다 **ctrl + f 5**합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-159">You can run the code and see results by pressing **ctrl-f5**.</span></span>  <span data-ttu-id="f2e60-160">디버깅 하지 않고 프로그램 실행 되 고 결과 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-160">This will run the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="f2e60-161">선택할 수 있습니다는 **디버그** 최상위 메뉴는 Visual Studio에서 항목을 선택 **디버깅 하지 않고 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-161">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="f2e60-162">이제 Visual Studio가 팝업를 콘솔 창에 출력할지 다음을 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-162">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="f2e60-163">지금까지</span><span class="sxs-lookup"><span data-stu-id="f2e60-163">Congratulations!</span></span>  <span data-ttu-id="f2e60-164">첫 번째 F # 프로젝트를 Visual Studio에서 만든 하 고, F # 함수는 해당 함수 호출의 결과 인쇄를 작성 하 고, 몇 가지 결과 보려면 프로젝트를 실행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-164">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f2e60-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f2e60-165">Next steps</span></span>

<span data-ttu-id="f2e60-166">아직 하지 않는 경우 체크 아웃의 [둘러보기의 F #](../tour.md)는 F # 언어의 핵심 기능 중 일부에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="f2e60-167">F #의 기능 중 일부에 대 한 개요를 제공 하 고 Visual Studio로 복사 하 고 실행할 수 있는 충분 한 코드 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="f2e60-168">사용할 수는 몇 가지 외부 리소스는 또한에서 보여 줍니다는 [F # 가이드](../index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f2e60-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2e60-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="f2e60-169">See also</span></span>
 [<span data-ttu-id="f2e60-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="f2e60-170">Visual F#</span></span>](index.md)  
 [<span data-ttu-id="f2e60-171">F# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="f2e60-171">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="f2e60-172">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="f2e60-172">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="f2e60-173">형식 유추</span><span class="sxs-lookup"><span data-stu-id="f2e60-173">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="f2e60-174">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="f2e60-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
