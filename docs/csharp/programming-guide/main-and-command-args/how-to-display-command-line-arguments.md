---
title: "방법: 명령줄 인수 표시(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cf8a57cce252b3596f0a19c9df643427615467c6
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a><span data-ttu-id="231b3-102">방법: 명령줄 인수 표시(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="231b3-102">How to: Display Command Line Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="231b3-103">명령줄에서 실행 파일에 제공된 인수는 `Main`에 대한 선택적 매개 변수를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231b3-103">Arguments provided to an executable on the command-line are accessible through an optional parameter to `Main`.</span></span> <span data-ttu-id="231b3-104">인수는 문자열 배열의 형태로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="231b3-104">The arguments are provided in the form of an array of strings.</span></span> <span data-ttu-id="231b3-105">배열의 각 요소에는 하나의 인수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231b3-105">Each element of the array contains one argument.</span></span> <span data-ttu-id="231b3-106">인수 사이의 공백은 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="231b3-106">White-space between arguments is removed.</span></span> <span data-ttu-id="231b3-107">예를 들어 명령줄에서 다음과 같이 가상 실행 파일을 호출한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="231b3-107">For example, consider these command-line invocations of a fictitious executable:</span></span>  
  
|<span data-ttu-id="231b3-108">명령줄 입력</span><span class="sxs-lookup"><span data-stu-id="231b3-108">Input on Command-line</span></span>|<span data-ttu-id="231b3-109">Main에 전달되는 문자열 배열</span><span class="sxs-lookup"><span data-stu-id="231b3-109">Array of strings passed to Main</span></span>|  
|----------------------------|-------------------------------------|  
|<span data-ttu-id="231b3-110">**executable.exe a b c**</span><span class="sxs-lookup"><span data-stu-id="231b3-110">**executable.exe a b c**</span></span>|<span data-ttu-id="231b3-111">"a"</span><span class="sxs-lookup"><span data-stu-id="231b3-111">"a"</span></span><br /><br /> <span data-ttu-id="231b3-112">"b"</span><span class="sxs-lookup"><span data-stu-id="231b3-112">"b"</span></span><br /><br /> <span data-ttu-id="231b3-113">"c"</span><span class="sxs-lookup"><span data-stu-id="231b3-113">"c"</span></span>|  
|<span data-ttu-id="231b3-114">**executable.exe one two**</span><span class="sxs-lookup"><span data-stu-id="231b3-114">**executable.exe one two**</span></span>|<span data-ttu-id="231b3-115">"one"</span><span class="sxs-lookup"><span data-stu-id="231b3-115">"one"</span></span><br /><br /> <span data-ttu-id="231b3-116">"two"</span><span class="sxs-lookup"><span data-stu-id="231b3-116">"two"</span></span>|  
|<span data-ttu-id="231b3-117">**executable.exe "one two" three**</span><span class="sxs-lookup"><span data-stu-id="231b3-117">**executable.exe "one two" three**</span></span>|<span data-ttu-id="231b3-118">"one two"</span><span class="sxs-lookup"><span data-stu-id="231b3-118">"one two"</span></span><br /><br /> <span data-ttu-id="231b3-119">"three"</span><span class="sxs-lookup"><span data-stu-id="231b3-119">"three"</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="231b3-120">Visual Studio에서 응용 프로그램을 실행할 경우 [프로젝트 디자이너, 디버그 페이지](/visualstudio/ide/reference/debug-page-project-designer)에서 명령줄 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="231b3-120">When you are running an application in Visual Studio, you can specify command-line arguments in the [Debug Page, Project Designer](/visualstudio/ide/reference/debug-page-project-designer).</span></span>  
  
## <a name="example"></a><span data-ttu-id="231b3-121">예제</span><span class="sxs-lookup"><span data-stu-id="231b3-121">Example</span></span>  
 <span data-ttu-id="231b3-122">이 예제에서는 명령줄 응용 프로그램에 전달된 명령줄 인수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="231b3-122">This example displays the command line arguments passed to a command-line application.</span></span> <span data-ttu-id="231b3-123">위의 표에서 첫 번째 항목에 대한 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="231b3-123">The output shown is for the first entry in the table above.</span></span>  
  
 <span data-ttu-id="231b3-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="231b3-124">[!code-cs[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="231b3-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="231b3-125">See Also</span></span>  
 <span data-ttu-id="231b3-126">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="231b3-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="231b3-127">[csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span><span class="sxs-lookup"><span data-stu-id="231b3-127">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) </span></span>  
 <span data-ttu-id="231b3-128">[Main()과 명령줄 인수](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="231b3-128">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 <span data-ttu-id="231b3-129">[방법: foreach를 사용하여 명령줄 인수 액세스](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span><span class="sxs-lookup"><span data-stu-id="231b3-129">[How to: Access Command-Line Arguments Using foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md) </span></span>  
 [<span data-ttu-id="231b3-130">Main() 반환 값</span><span class="sxs-lookup"><span data-stu-id="231b3-130">Main() Return Values</span></span>](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)

