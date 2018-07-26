---
title: 'Visual Studio에서 F # 시작'
description: 'Visual Studio를 사용 하 여 F #을 사용 하는 방법에 알아봅니다.'
ms.date: 07/03/2018
ms.openlocfilehash: a4a12a322d7e5144f2d720541f6ef65ca12737dd
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874717"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="94cca-103">Visual Studio에서 F # 시작</span><span class="sxs-lookup"><span data-stu-id="94cca-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="94cca-104">F # 및 Visual F # 도구는 Visual Studio IDE에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="94cca-105">시작 하려면 했는지 [F #을 사용 하 여 설치 된 Visual Studio](install-fsharp.md#install-f-with-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="94cca-106">콘솔 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="94cca-106">Creating a console application</span></span>

<span data-ttu-id="94cca-107">Visual Studio에서 가장 기본적인 프로젝트 중 하나에 콘솔 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="94cca-108">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-108">Here's how to do it.</span></span>  <span data-ttu-id="94cca-109">Visual Studio가 열리면:</span><span class="sxs-lookup"><span data-stu-id="94cca-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="94cca-110">에 **파일** 메뉴에서 **새로 만들기**를 선택한 후 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="94cca-111">새 프로젝트에서 대화 상자에서 아래 **템플릿을**에 표시 됩니다 **Visual F #** 합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="94cca-112">F # 템플릿을 표시 하려면이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="94cca-113">선택 **.NET Core 콘솔 앱** 하거나 **콘솔 앱**합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-113">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="94cca-114">선택 된 **알겠습니다** F # 프로젝트를 만들려면 단추!</span><span class="sxs-lookup"><span data-stu-id="94cca-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="94cca-115">솔루션 탐색기에서 F # 프로젝트는 이제 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="94cca-116">코드 작성</span><span class="sxs-lookup"><span data-stu-id="94cca-116">Writing your code</span></span>

<span data-ttu-id="94cca-117">보겠습니다 먼저 일부 코드를 작성 하 여 시작 하세요.</span><span class="sxs-lookup"><span data-stu-id="94cca-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="94cca-118">했는지를 `Program.fs` 파일 열려 있는 경우 및 다음 해당 콘텐츠를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="94cca-119">이전 코드 샘플에서는 함수 `square` 명명 된 입력을 가져와서는 정의한 `x` 을 단독으로 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="94cca-120">F # 사용 하므로 [형식 유추](../language-reference/type-inference.md), 형식의 `x` 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="94cca-121">F # 컴파일러 곱하기 유효 형식에 대 한 이해 및 형식을 할당 합니다 `x` 하는 방법에 따라 `square` 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="94cca-122">위로 가져가면 `square`, 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-122">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="94cca-123">이 함수 형식 시그니처 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="94cca-124">다음과 같이 읽을 수 있습니다: "정사각형은 명명 된 정수를 사용 하는 함수 x는 정수를 생성 하 고".</span><span class="sxs-lookup"><span data-stu-id="94cca-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="94cca-125">컴파일러 했습니다 보면 `square` 를 `int` 형식 곱하기에서 제네릭 없기 때문에 이것이-지금은 *모든* 형식 이지만 대신 제네릭 형식의 폐쇄형 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="94cca-126">선택 하는 F # 컴파일러 `int` 지금은 지점 하지만 조정 됩니다 형식 시그니처 호출 하는 경우 `square` 다른 입력 형식에 같은 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="94cca-127">다른 함수를 `main`, 정의 된으로 데코 레이트 된는 `EntryPoint` F # 컴파일러는 프로그램 실행에 지시 하는 특성 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="94cca-128">다른 동일한 규칙을 따릅니다 [C 스타일 프로그래밍 언어](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), 여기서이 함수에 명령줄 인수를 전달할 수 있습니다 및 정수 코드가 반환 됩니다 (일반적으로 `0`).</span><span class="sxs-lookup"><span data-stu-id="94cca-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="94cca-129">이 함수를 호출 하는 것은 `square` 의 인수를 사용 하 여 함수 `12`합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="94cca-130">F # 컴파일러에는 다음 형식의 할당 `square` 되도록 `int -> int` (사용 하는 함수,는 `int` 생성 하 고는 `int`).</span><span class="sxs-lookup"><span data-stu-id="94cca-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="94cca-131">에 대 한 호출 `printfn` 은 형식 문자열에 지정 된 해당 하는 매개 변수를 C 스타일 프로그래밍 언어와 유사한 형식 문자열을 사용 하는 서식이 지정 된 인쇄 기능 및 다음 결과 새 줄을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="94cca-132">코드 실행</span><span class="sxs-lookup"><span data-stu-id="94cca-132">Running your code</span></span>

<span data-ttu-id="94cca-133">코드를 실행 하 고 키를 눌러 결과 볼 수 있습니다 **ctrl-f5**합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-133">You can run the code and see results by pressing **ctrl-f5**.</span></span>  <span data-ttu-id="94cca-134">이 디버깅 하지 않고 프로그램을 실행 및 결과 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-134">This will run the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="94cca-135">선택할 수 있습니다 합니다 **디버깅할** 최상위 메뉴 항목 Visual Studio에서 선택한 **디버깅 하지 않고 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="94cca-136">이제 Visual Studio를 나타나게 하는 콘솔 창에 출력 한 다음을 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="94cca-137">지금까지</span><span class="sxs-lookup"><span data-stu-id="94cca-137">Congratulations!</span></span>  <span data-ttu-id="94cca-138">Visual Studio에서 첫 번째 F # 프로젝트를 생성 하 고는 F # 함수는 함수 호출의 결과 출력을 작성 하 고, 일부 결과 보려면 프로젝트를 실행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="94cca-139">다음 단계</span><span class="sxs-lookup"><span data-stu-id="94cca-139">Next steps</span></span>

<span data-ttu-id="94cca-140">이미 않았다면 체크 아웃 합니다 [F # 둘러보기](../tour.md), F # 언어의 핵심 기능 중 일부를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="94cca-141">F #의 기능 중 일부의 개요를 제공 하 고 Visual Studio로 복사 하 고 실행할 수 있는 충분 한 코드 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="94cca-142">도 유용한 외부 리소스 사용할 수 있습니다에 표시 된 [F # 가이드](../index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94cca-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="94cca-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="94cca-143">See also</span></span>
 <span data-ttu-id="94cca-144">[F # 둘러보기](../tour.md) [F # 언어 참조](../language-reference/index.md) [형식 유추](../language-reference/type-inference.md) [기호 및 연산자 참조](../language-reference/symbol-and-operator-reference/index.md)</span><span class="sxs-lookup"><span data-stu-id="94cca-144">[Tour of F#](../tour.md) [F# language reference](../language-reference/index.md) [Type inference](../language-reference/type-inference.md) [Symbol and operator reference](../language-reference/symbol-and-operator-reference/index.md)</span></span>
