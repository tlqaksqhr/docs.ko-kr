---
title: 'Mac 용 Visual Studio에서 F #으로 시작'
description: 'F # Visual Studio와 함께 사용할 Mac. 하는 방법을 알아봅니다'
ms.date: 02/13/2017
ms.openlocfilehash: 58e65e703b092f2ee5d74386051b158c932013b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565560"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="ad594-103">Mac 용 Visual Studio에서 F #으로 시작</span><span class="sxs-lookup"><span data-stu-id="ad594-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="ad594-104">F # 및 Visual F # 도구는 Mac IDE에 대 한 Visual Studio에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span>  <span data-ttu-id="ad594-105">를 시작 하려면 [Mac 용 Visual Studio 다운로드](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)아직 없는 경우, 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-105">To begin, you should [download Visual Studio for Mac](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs), if you haven't already.</span></span>  <span data-ttu-id="ad594-106">이 문서에서는, Mac 용 Visual Studio 커뮤니티 2017을 사용 하지만 사용할 수 있습니다 F # 원하는 버전으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-106">This article uses the Visual Studio Community 2017 for Mac, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="ad594-107">F # 설치</span><span class="sxs-lookup"><span data-stu-id="ad594-107">Installing F#</span></span> #

<span data-ttu-id="ad594-108">Mac 용 Visual Studio를 다운로드 한 후이 옵션은 요청 설치를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-108">After downloading Visual Studio for Mac, it will prompt you to choose what you want to install.</span></span>  <span data-ttu-id="ad594-109">이 문서의 목적에 대 한 우리 기본값 그대로 두고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-109">For the purposes of this article we will be leaving the defaults.</span></span>  <span data-ttu-id="ad594-110">Visual Studio for Windows를 달리 구체적으로 F # 지원을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-110">In contrast to Visual Studio for Windows, you do not need to specifically install F# support.</span></span>  <span data-ttu-id="ad594-111">계속 하려면 "설치"를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-111">Press "Install" to proceed.</span></span>

<span data-ttu-id="ad594-112">설치가 완료 된 후 "Visual Studio 시작"을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-112">After the install completes, choose "Start Visual Studio".</span></span>  <span data-ttu-id="ad594-113">또한 macOS에서 파인더를 통해 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-113">You can also launch it through Finder on macOS.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="ad594-114">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="ad594-114">Creating a console application</span></span>

<span data-ttu-id="ad594-115">Mac 용 Visual Studio에서 가장 기본적인 프로젝트 중 하나는 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-115">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="ad594-116">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-116">Here's how to do it.</span></span>  <span data-ttu-id="ad594-117">Mac 용 Visual Studio를 열면:</span><span class="sxs-lookup"><span data-stu-id="ad594-117">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="ad594-118">에 **파일** 메뉴에서 **새 솔루션**합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-118">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="ad594-119">새 프로젝트 대화 상자는 콘솔 응용 프로그램에 대 한 2 개의 서로 다른 템플릿을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-119">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="ad594-120">기타에서 하나의.NET Framework를 대상으로 하는.NET->.</span><span class="sxs-lookup"><span data-stu-id="ad594-120">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="ad594-121">.NET Core에서 다른 서식 파일은.NET Core를 대상으로 하는 응용 프로그램-> 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-121">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="ad594-122">이 문서 템플릿 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-122">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="ad594-123">콘솔 응용 프로그램에서 C# F #에 필요한 경우 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-123">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="ad594-124">선택 된 **다음** 앞으로 이동 하려면 단추!</span><span class="sxs-lookup"><span data-stu-id="ad594-124">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="ad594-125">프로젝트에 이름을 지정 하 고 응용 프로그램에 사용할 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-125">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="ad594-126">선택한 옵션을 기반으로 생성 되는 디렉터리 구조를 표시 하는 화면의 측면에 미리 보기 창, 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-126">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="ad594-127">**만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-127">Click **Create**.</span></span>  <span data-ttu-id="ad594-128">이제 F # 프로젝트를 솔루션 탐색기에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-128">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="ad594-129">코드 작성</span><span class="sxs-lookup"><span data-stu-id="ad594-129">Writing your code</span></span>

<span data-ttu-id="ad594-130">이제 시작 하겠습니다 먼저 일부 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-130">Let's get started by writing some code first.</span></span>  <span data-ttu-id="ad594-131">다음 사항을 확인는 `Program.fs` 파일을 연 상태 및 다음 내용에 다음을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-131">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="ad594-132">이전 코드 예제에서 함수 `square` 라는 입력을 가져와서는 정의 된 `x` 여 스스로 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-132">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="ad594-133">F #에서 사용 하기 때문에 [형식 유추](../language-reference/type-inference.md), 유형의 `x` 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-133">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="ad594-134">F # 컴파일러 곱하기 올바른지 종류를 이해 하 고에 형식을 할당 합니다 `x` 정도에 따라 `square` 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-134">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="ad594-135">위로 가져가면 `square`, 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-135">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="ad594-136">이 함수의 형식 서명이 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-136">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="ad594-137">다음과 같이 읽을 수 있습니다: "사각형 이라는 정수를 사용 하는 함수는 x는 정수를 생성 하 고"입니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-137">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="ad594-138">지정 하는 컴파일러는 `square` 는 `int` 형식 곱하기에서 제네릭 없기 때문에 이것이 지금은- *모든* 형식, 하지만 대신는 제네릭 형식의 폐쇄형 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-138">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="ad594-139">선택 하는 F # 컴파일러 `int` 이 지점 하지만 메이커가 형식 시그니처 호출 하는 경우 `square` 가 다른 입력 형식, 같은 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-139">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="ad594-140">다른 함수 `main`, 정의 된으로 데코레이팅되 어는 `EntryPoint` 해당 프로그램 실행 F # 컴파일러에 지시 하는 특성 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-140">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="ad594-141">다른 동일한 규칙에 따라 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), 여기서이 함수에 전달할 수 있는 명령줄 인수 및 정수 코드가 반환 됩니다 (일반적으로 `0`).</span><span class="sxs-lookup"><span data-stu-id="ad594-141">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="ad594-142">이라고 하는이 함수에는 `square` 의 인수와 함께 함수가 `12`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-142">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="ad594-143">F # 컴파일러에는 다음 형식의 할당 `square` 되도록 `int -> int` (사용 되는 함수, 즉는 `int` 하 고 생성 한 `int`).</span><span class="sxs-lookup"><span data-stu-id="ad594-143">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="ad594-144">에 대 한 호출 `printfn` 은 형식 문자열에 지정 하는 것에 해당 하는 매개 변수를 C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용 하 여 형식이 지정 된 인쇄 기능 한 다음 결과 새 줄을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-144">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="ad594-145">코드 실행</span><span class="sxs-lookup"><span data-stu-id="ad594-145">Running your code</span></span>

<span data-ttu-id="ad594-146">코드를 실행 하 고 클릭 하 여 결과 볼 수 **실행** 최상위 메뉴에서 다음 **디버깅 하지 않고 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-146">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="ad594-147">디버깅 하지 않고 프로그램 실행 되 고 결과 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-147">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="ad594-148">이제 다음 Mac 용 Visual Studio가 팝업를 콘솔 창에 출력할지 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-148">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="ad594-149">지금까지</span><span class="sxs-lookup"><span data-stu-id="ad594-149">Congratulations!</span></span>  <span data-ttu-id="ad594-150">Mac 용 Visual Studio에서 첫 번째 F # 프로젝트를 만든 하 고, F # 함수는 해당 함수 호출의 결과 인쇄를 작성 하 고, 몇 가지 결과 보려면 프로젝트를 실행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-150">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="ad594-151">F # Interactive를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="ad594-151">Using F# Interactive</span></span>

<span data-ttu-id="ad594-152">Visual F # Mac 용 도구 Visual Studio에서 가장 유용한 기능 중 하나에 F # Interactive 창입니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-152">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="ad594-153">해당 코드를 호출 하 고 결과 대화형으로 확인할 수 있는 프로세스에 코드를 통해 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-153">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="ad594-154">사용을 시작 하려면 강조 표시는 `square` 코드에 정의 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-154">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="ad594-155">차례 대로 클릭 **편집** 최상위 메뉴에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-155">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="ad594-156">다음으로 **선택 F # Interactive로 보내기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-156">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="ad594-157">F # 대화형 창에서 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-157">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="ad594-158">선택 영역을 마우스 오른쪽 단추로 클릭 하 고 선택할 수 있습니다 또는 **선택 F # Interactive로 보내기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-158">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="ad594-159">F # 대화형 표시 되는 창에 다음과 같이 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-159">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="ad594-160">에 대 한 동일한 함수 시그니처 표시는 `square` 함수 위로 가져갈 때 앞에서 본 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-160">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="ad594-161">때문에 `square` 은 F # Interactive 프로세스에 정의 된, 이제 서로 다른 값으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-161">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="ad594-162">이 함수를 실행, 결과 새 이름 바인딩합니다 `it`, 유형 및 값을 표시 하 고 `it`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-162">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="ad594-163">각 줄을 종료 해야 참고 `;;`합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-163">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="ad594-164">이 어떻게 F # Interactive 알고 함수 호출이 완료 되 면입니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-164">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="ad594-165">또한 F # Interactive에서 새로운 함수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-165">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="ad594-166">위의 정의 새 함수로 `isOdd`,이 `int` 홀수 인지를 확인 하 고!</span><span class="sxs-lookup"><span data-stu-id="ad594-166">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="ad594-167">반환 서로 다른 입력을 확인 하려면이 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-167">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="ad594-168">함수 호출 내에서 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-168">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="ad594-169">사용할 수도 있습니다는 [정방향 파이프 연산자](../language-reference/symbol-and-operator-reference/index.md) 값 두 함수에 파이프라인 할:</span><span class="sxs-lookup"><span data-stu-id="ad594-169">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="ad594-170">정방향 파이프 연산자 등은 이후 자습서에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-170">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="ad594-171">이것은 F # 대화형으로 수행할 수 있는에 간략만 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-171">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="ad594-172">자세한 내용을 보려면 체크 아웃 [F #을 사용한 대화형 프로그래밍](../tutorials/fsharp-interactive/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-172">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ad594-173">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ad594-173">Next steps</span></span>

<span data-ttu-id="ad594-174">아직 하지 않는 경우 체크 아웃의 [둘러보기의 F #](../tour.md)는 F # 언어의 핵심 기능 중 일부에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-174">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="ad594-175">F #의 기능 중 일부에 대 한 개요를 제공 하 고 Mac 용 Visual Studio로 복사 하 고 실행할 수 있는 충분 한 코드 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-175">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="ad594-176">사용할 수는 몇 가지 외부 리소스는 또한에서 보여 줍니다는 [F # 가이드](../index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad594-176">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ad594-177">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad594-177">See also</span></span>
 [<span data-ttu-id="ad594-178">Visual F#</span><span class="sxs-lookup"><span data-stu-id="ad594-178">Visual F#</span></span>](../index.md)  
 [<span data-ttu-id="ad594-179">F# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="ad594-179">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="ad594-180">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="ad594-180">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="ad594-181">형식 유추</span><span class="sxs-lookup"><span data-stu-id="ad594-181">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="ad594-182">기호 및 연산자 참조</span><span class="sxs-lookup"><span data-stu-id="ad594-182">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
