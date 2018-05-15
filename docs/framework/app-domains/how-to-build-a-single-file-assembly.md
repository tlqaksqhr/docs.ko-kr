---
title: '방법: 단일 파일 어셈블리 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6aa39671da519ebf54dad52638ab940897209517
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="76421-102">방법: 단일 파일 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="76421-102">How to: Build a Single-File Assembly</span></span>
<span data-ttu-id="76421-103">가장 단순한 형식의 어셈블리인 단일 파일 어셈블리에는 형식 정보 및 구현과 [어셈블리 매니페스트](../../../docs/framework/app-domains/assembly-manifest.md)가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76421-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="76421-104">명령줄 컴파일러 또는 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]를 사용하여 단일 파일 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76421-104">You can use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to create a single-file assembly.</span></span> <span data-ttu-id="76421-105">기본적으로 컴파일러는 확장명이 .exe인 어셈블리 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76421-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76421-106">C# 및 Visual Basic용 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]는 단일 파일 어셈블리를 만드는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76421-106">[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="76421-107">다중 파일 어셈블리를 만들려면 명령줄 컴파일러나 Visual C++용 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76421-107">If you want to create multifile assemblies, you must use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for Visual C++.</span></span>  
  
 <span data-ttu-id="76421-108">다음 절차에는 명령줄 컴파일러를 사용하여 단일 파일 어셈블리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76421-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="76421-109">확장명이 .exe인 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="76421-109">To create an assembly with an .exe extension</span></span>  
  
1.  <span data-ttu-id="76421-110">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="76421-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="76421-111">\<*compiler command*> \<*module name*></span><span class="sxs-lookup"><span data-stu-id="76421-111">\<*compiler command*> \<*module name*></span></span>  
  
     <span data-ttu-id="76421-112">이 명령에서 *compiler command*는 코드 모듈에서 사용되는 언어에 대한 컴파일러 명령이고, *module name*은 어셈블리로 컴파일할 코드 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76421-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="76421-113">다음 예제에서는 `myCode`라는 코드 모듈에서 `myCode.exe` 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76421-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>  
  
```console
csc myCode.cs  
```  

```console
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="76421-114">확장명이 .exe인 어셈블리를 만들고 출력 파일 이름을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="76421-114">To create an assembly with an .exe extension and specify the output file name</span></span>  
  
1.  <span data-ttu-id="76421-115">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="76421-115">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="76421-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span><span class="sxs-lookup"><span data-stu-id="76421-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>  
  
     <span data-ttu-id="76421-117">이 명령에서 *compiler command*는 코드 모듈에서 사용되는 언어에 대한 컴파일러 명령이고, *file name*은 출력 파일 이름이고, *module name*은 어셈블리로 컴파일할 코드 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76421-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="76421-118">다음 예제에서는 `myCode`라는 코드 모듈에서 `myAssembly.exe` 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76421-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myAssembly.exe myCode.cs  
```  
  
```console
vbc -out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a><span data-ttu-id="76421-119">라이브러리 어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="76421-119">Creating Library Assemblies</span></span>  
 <span data-ttu-id="76421-120">라이브러리 어셈블리는 클래스 라이브러리와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="76421-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="76421-121">다른 어셈블리에서 참조되는 형식을 포함하지만 실행을 시작할 진입점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76421-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>  
  
#### <a name="to-create-a-library-assembly"></a><span data-ttu-id="76421-122">라이브러리 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="76421-122">To create a library assembly</span></span>  
  
1.  <span data-ttu-id="76421-123">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="76421-123">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="76421-124">\<*compiler command*> **-t:library** \<*module name*></span><span class="sxs-lookup"><span data-stu-id="76421-124">\<*compiler command*> **-t:library** \<*module name*></span></span>  
  
     <span data-ttu-id="76421-125">이 명령에서 *compiler command*는 코드 모듈에서 사용되는 언어에 대한 컴파일러 명령이고, *module name*은 어셈블리로 컴파일할 코드 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76421-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="76421-126">**-out:** 옵션 등의 다른 컴파일러 옵션을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76421-126">You can also use other compiler options, such as the **-out:** option.</span></span>  
  
 <span data-ttu-id="76421-127">다음 예제에서는 `myCode`라는 코드 모듈에서 `myCodeAssembly.dll`이라는 라이브러리 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76421-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myCodeLibrary.dll -t:library myCode.cs  
```  
  
```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="76421-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76421-128">See Also</span></span>  
 [<span data-ttu-id="76421-129">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="76421-129">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="76421-130">다중 파일 어셈블리</span><span class="sxs-lookup"><span data-stu-id="76421-130">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 [<span data-ttu-id="76421-131">방법: 다중 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="76421-131">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="76421-132">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="76421-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
