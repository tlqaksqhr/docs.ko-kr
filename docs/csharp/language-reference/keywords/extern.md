---
title: "extern(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- extern_CSharpKeyword
- extern
dev_langs:
- CSharp
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: 26
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
ms.openlocfilehash: e499ade5ec8a9339b0d425c59809cf7c177466fb
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="extern-c-reference"></a><span data-ttu-id="3e372-102">extern(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="3e372-102">extern (C# Reference)</span></span>
<span data-ttu-id="3e372-103">`extern` 한정자는 외부에서 구현되는 메서드를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-103">The `extern` modifier is used to declare a method that is implemented externally.</span></span> <span data-ttu-id="3e372-104">`extern` 한정자는 일반적으로 Interop 서비스를 사용하여 비관리 코드를 호출할 때 `DllImport` 특성과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-104">A common use of the `extern` modifier is with the `DllImport` attribute when you are using Interop services to call into unmanaged code.</span></span> <span data-ttu-id="3e372-105">이 경우 다음 예제에서와 같이 메서드를 `static`으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-105">In this case, the method must also be declared as `static`, as shown in the following example:</span></span>  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 <span data-ttu-id="3e372-106">`extern` 키워드는 외부 어셈블리 별칭도 정의하여 단일 어셈블리 내에서 동일한 구성 요소의 다른 버전을 참조할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-106">The `extern` keyword can also define an external assembly alias, which makes it possible to reference different versions of the same component from within a single assembly.</span></span> <span data-ttu-id="3e372-107">자세한 내용은 [extern alias](../../../csharp/language-reference/keywords/extern-alias.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e372-107">For more information, see [extern alias](../../../csharp/language-reference/keywords/extern-alias.md).</span></span>  
  
 <span data-ttu-id="3e372-108">[abstract](../../../csharp/language-reference/keywords/abstract.md) 및 `extern` 한정자를 함께 사용하여 같은 멤버를 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-108">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) and `extern` modifiers together to modify the same member.</span></span> <span data-ttu-id="3e372-109">`extern` 한정자는 메서드가 C# 코드 외부에서 구현됨을 나타내고 `abstract` 한정자는 해당 클래스에서 메서드가 구현되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-109">Using the `extern` modifier means that the method is implemented outside the C# code, whereas using the `abstract` modifier means that the method implementation is not provided in the class.</span></span>  
  
 <span data-ttu-id="3e372-110">extern 키워드는 C++보다 C#에서 사용이 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-110">The extern keyword has more limited uses in C# than in C++.</span></span> <span data-ttu-id="3e372-111">C# 키워드를 C++ 키워드와 비교하려면 extern을 사용하여 C++ 언어 참조에 링크 지정을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e372-111">To compare the C# keyword with the C++ keyword, see Using extern to Specify Linkage in the C++ Language Reference.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e372-112">예제</span><span class="sxs-lookup"><span data-stu-id="3e372-112">Example</span></span>  
 <span data-ttu-id="3e372-113">**예제 1.**</span><span class="sxs-lookup"><span data-stu-id="3e372-113">**Example 1.**</span></span> <span data-ttu-id="3e372-114">이 예제에서는 프로그램이 사용자로부터 문자열을 수신하여 메시지 상자에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-114">In this example, the program receives a string from the user and displays it inside a message box.</span></span> <span data-ttu-id="3e372-115">이 프로그램은 User32.dll 라이브러리에서 가져온 `MessageBox` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-115">The program uses the `MessageBox` method imported from the User32.dll library.</span></span>  
  
 <span data-ttu-id="3e372-116">[!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3e372-116">[!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e372-117">예제</span><span class="sxs-lookup"><span data-stu-id="3e372-117">Example</span></span>  
 <span data-ttu-id="3e372-118">**예제 2.**</span><span class="sxs-lookup"><span data-stu-id="3e372-118">**Example 2.**</span></span> <span data-ttu-id="3e372-119">이 예제는 C 라이브러리(네이티브 DLL)로 호출되는 C# 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-119">This example illustrates a C# program that calls into a C library (a native DLL).</span></span>  
  
 1. <span data-ttu-id="3e372-120">다음 C 파일을 만들고 이름을 `cmdll.c`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-120">Create the following C file and name it `cmdll.c`:</span></span>  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## <a name="example"></a><span data-ttu-id="3e372-121">예제</span><span class="sxs-lookup"><span data-stu-id="3e372-121">Example</span></span>  
 2. <span data-ttu-id="3e372-122">Visual Studio 설치 디렉터리에서 Visual Studio x64(또는 x32) 네이티브 도구 명령 프롬프트 창을 열고 명령 프롬프트에서 **cl /LD cmdll.c**를 입력하여 `cmdll.c` 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-122">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cmdll.c` file by typing **cl /LD cmdll.c** at the command prompt.</span></span>  
  
 3. <span data-ttu-id="3e372-123">같은 디렉터리에서 다음 C# 파일을 만들고 이름을 `cm.cs`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-123">In the same directory, create the following C# file and name it `cm.cs`:</span></span>  
  
```  
// cm.cs  
using System;  
using System.Runtime.InteropServices;  
public class MainClass   
{  
   [DllImport("Cmdll.dll")]  
   public static extern int SampleMethod(int x);  
  
   static void Main()   
   {  
      Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="3e372-124">예제</span><span class="sxs-lookup"><span data-stu-id="3e372-124">Example</span></span>  
 3. <span data-ttu-id="3e372-125">Visual Studio 설치 디렉터리에서 Visual Studio x64(또는 x32) 네이티브 도구 명령 프롬프트 창을 열고 명령 프롬프트에서 다음을 입력하여 `cm.cs` 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-125">Open a Visual Studio x64 (or x32) Native Tools Command Prompt window from the Visual Studio installation directory and compile the `cm.cs` file by typing:</span></span>  
  
> <span data-ttu-id="3e372-126">**csc cm.cs**(x64 명령 프롬프트의 경우)</span><span class="sxs-lookup"><span data-stu-id="3e372-126">**csc cm.cs** (for the x64 command prompt)</span></span>   
>  <span data-ttu-id="3e372-127">또는</span><span class="sxs-lookup"><span data-stu-id="3e372-127">—or—</span></span>  
> <span data-ttu-id="3e372-128">**csc /platform:x86 cm.cs**(x32 명령 프롬프트의 경우)</span><span class="sxs-lookup"><span data-stu-id="3e372-128">**csc /platform:x86 cm.cs** (for the x32 command prompt)</span></span>  
  
 <span data-ttu-id="3e372-129">이렇게 하면 실행 파일 `cm.exe`가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-129">This will create the executable file `cm.exe`.</span></span>  
  
 4. <span data-ttu-id="3e372-130">`cm.exe`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-130">Run `cm.exe`.</span></span> <span data-ttu-id="3e372-131">`SampleMethod` 메서드가 값 5를 DLL 파일에 전달하면 10을 곱한 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-131">The `SampleMethod` method passes the value 5 to the DLL file, which returns the value multiplied by 10.</span></span>  <span data-ttu-id="3e372-132">프로그램에서는 다음이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e372-132">The program produces the following output:</span></span>  
  
```  
SampleMethod() returns 50.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="3e372-133">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="3e372-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e372-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e372-134">See Also</span></span>  
 <span data-ttu-id="3e372-135"><xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="3e372-135"><xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName></span></span>   
 <span data-ttu-id="3e372-136">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3e372-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3e372-137">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3e372-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3e372-138">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3e372-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="3e372-139">한정자</span><span class="sxs-lookup"><span data-stu-id="3e372-139">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

