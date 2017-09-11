---
title: "데스크톱 응용 프로그램용 리소스 파일 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource files, .resources files
- .resources files
- application resources, creating files
- resource files, creating
ms.assetid: 6c5ad891-66a0-4e7a-adcf-f41863ba6d8d
caps.latest.revision: 25
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2afcde97f5056c23f8d6bc294e955b75b5f166fd
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="creating-resource-files-for-desktop-apps"></a><span data-ttu-id="7d970-102">데스크톱 응용 프로그램용 리소스 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="7d970-102">Creating Resource Files for Desktop Apps</span></span>
<span data-ttu-id="7d970-103">문자열, 이미지 또는 개체 데이터와 같은 리소스를 리소스 파일에 포함하여 응용 프로그램에서 쉽게 사용할 수 있게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-103">You can include resources, such as strings, images, or object data, in resources files to make them easily available to your application.</span></span> <span data-ttu-id="7d970-104">.NET Framework에서는 리소스 파일을 만드는 다섯 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-104">The .NET Framework offers five ways to create resources files:</span></span>  
  
-   <span data-ttu-id="7d970-105">문자열 리소스가 포함된 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-105">Create a text file that contains string resources.</span></span> <span data-ttu-id="7d970-106">[리소스 파일 생성기(Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 텍스트 파일을 이진 리소스(.resources) 파일로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-106">You can use [Resource File Generator (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) to convert the text file into a binary resource (.resources) file.</span></span> <span data-ttu-id="7d970-107">그다음에 언어 컴파일러를 사용하여 이진 리소스 파일을 응용 프로그램 실행 파일 또는 응용 프로그램 라이브러리에 포함하거나, [어셈블리 링커(Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-107">You can then embed the binary resource file  in an application executable or an application library by using a language compiler, or you can embed it in a satellite assembly by using [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="7d970-108">자세한 내용은 [텍스트 파일의 리소스](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#TextFiles) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-108">For more information, see the [Resources in Text Files](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#TextFiles) section.</span></span>  
  
-   <span data-ttu-id="7d970-109">문자열, 이미지 또는 개체 데이터가 포함된 XML 리소스(.resx) 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-109">Create an XML resource (.resx) file that contains string, image, or object data.</span></span> <span data-ttu-id="7d970-110">[리소스 파일 생성기(Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 .resx 파일을 이진 리소스(.resources) 파일로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-110">You can use [Resource File Generator (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) to convert the .resx file into a binary resource (.resources) file.</span></span> <span data-ttu-id="7d970-111">그다음에 언어 컴파일러를 사용하여 이진 리소스 파일을 응용 프로그램 실행 파일 또는 응용 프로그램 라이브러리에 포함하거나, [어셈블리 링커(Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-111">You can then embed the binary resource file in an application executable or an application library by using a language compiler, or you can embed it in a satellite assembly by using [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="7d970-112">자세한 내용은 [.resx 파일의 리소스](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResxFiles) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-112">For more information, see the [Resources in .resx Files](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResxFiles) section.</span></span>  
  
-   <span data-ttu-id="7d970-113"><xref:System.Resources> 네임스페이스의 형식을 사용하여 프로그래밍 방식으로 XML 리소스(.resx) 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-113">Create an XML resource (.resx) file programmatically by using types in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="7d970-114">.resx 파일을 만들고, 해당 리소스를 열거하고, 특정 리소스를 이름으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-114">You can create a .resx file, enumerate its resources, and retrieve specific resources by name.</span></span> <span data-ttu-id="7d970-115">자세한 내용은 [프로그래밍 방식으로 .resx 파일 작업](../../../docs/framework/resources/working-with-resx-files-programmatically.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-115">For more information, see the topic [Working with .resx Files Programmatically](../../../docs/framework/resources/working-with-resx-files-programmatically.md).</span></span>  
  
-   <span data-ttu-id="7d970-116">프로그래밍 방식으로 이진 리소스(.resources) 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-116">Create a binary resource (.resources) file programmatically.</span></span> <span data-ttu-id="7d970-117">그다음에 언어 컴파일러를 사용하여 파일을 응용 프로그램 실행 파일 또는 응용 프로그램 라이브러리에 포함하거나, [어셈블리 링커(Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-117">You can then embed the file in an application executable or an application library by using a language compiler, or you can embed it in a satellite assembly by using [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="7d970-118">자세한 내용은 [.resources 파일의 리소스](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResourcesFiles) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-118">For more information, see the [Resources in .resources Files](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResourcesFiles) section.</span></span>  
  
-   <span data-ttu-id="7d970-119">Visual Studio를 사용하여 리소스 파일을 만들고 프로젝트에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-119">Use Visual Studio to create a resource file and include it in your project.</span></span> <span data-ttu-id="7d970-120">Visual Studio에서는 리소스를 추가, 삭제 및 수정할 수 있는 리소스 편집기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-120">Visual Studio provides a resource editor that lets you add, delete, and modify resources.</span></span> <span data-ttu-id="7d970-121">컴파일 시간에 리소스 파일은 자동으로 이진 .resources 파일로 변환되고 응용 프로그램 어셈블리 또는 위성 어셈블리에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-121">At compile time, the resource file is automatically converted to a binary .resources file and embedded in an application assembly or satellite assembly.</span></span> <span data-ttu-id="7d970-122">자세한 내용은 [Visual Studio의 리소스 파일](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#VSResFiles) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-122">For more information, see the [Resource Files in Visual Studio](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#VSResFiles) section.</span></span>  
  
<a name="TextFiles"></a>   
## <a name="resources-in-text-files"></a><span data-ttu-id="7d970-123">텍스트 파일의 리소스</span><span class="sxs-lookup"><span data-stu-id="7d970-123">Resources in Text Files</span></span>  
 <span data-ttu-id="7d970-124">텍스트 파일(.txt 또는 .restext)을 사용하면 문자열 리소스만 저장할 수 있습니다. 문자열이 아닌 리소스의 경우 .resx 파일을 사용하거나 프로그래밍 방식으로 .resx 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-124">You can use text (.txt or .restext) files to store string resources only; for non-string resources, use .resx files or create them programmatically.</span></span> <span data-ttu-id="7d970-125">문자열 리소스가 포함된 텍스트 파일의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-125">Text files that contain string resources have the following format:</span></span>  
  
```  
# This is an optional comment.  
name = value  
  
; This is another optional comment.  
name = value  
  
; The following supports conditional compilation if X is defined.  
#ifdef X  
name1=value1  
name2=value2  
#endif  
  
# The following supports conditional compilation if Y is undefined.  
#if !Y  
name1=value1  
name2=value2  
#endif  
```  
  
 <span data-ttu-id="7d970-126">.txt 및 .restext 파일의 리소스 파일 형식은 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-126">The resource file format of .txt and .restext files is identical.</span></span> <span data-ttu-id="7d970-127">.restext 파일 확장명은 단순히 텍스트 파일을 텍스트 기반 리소스 파일로 즉시 식별할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-127">The .restext file extension merely serves to make text files immediately identifiable as text-based resource files.</span></span>  
  
 <span data-ttu-id="7d970-128">문자열 리소스는 *name/value* 쌍으로 나타납니다. 여기서 *name*은 리소스를 식별하는 문자열이고, *value*는 *name*을 <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>과 같은 리소스 검색 메서드에 전달할 때 반환되는 리소스 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-128">String resources appear as *name/value* pairs, where *name* is a string that identifies the resource, and *value* is the resource string that is returned when you pass *name* to a resource retrieval method such as <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="7d970-129">*name* 및 *value*는 등호(=)로 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-129">*name* and *value* must be separated by an equal sign (=).</span></span> <span data-ttu-id="7d970-130">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-130">For example:</span></span>  
  
```  
FileMenuName=File  
EditMenuName=Edit  
ViewMenuName=View  
HelpMenuName=Help  
```  
  
> [!CAUTION]
>  <span data-ttu-id="7d970-131">암호, 보안이 중요한 정보 또는 개인 데이터를 저장할 때는 리소스 파일을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-131">Do not use resource files to store passwords, security-sensitive information, or private data.</span></span>  
  
 <span data-ttu-id="7d970-132">빈 문자열(즉, <xref:System.String.Empty?displayProperty=fullName> 값을 가진 리소스)은 텍스트 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-132">Empty strings (that is, a resource whose value is <xref:System.String.Empty?displayProperty=fullName>) are permitted in text files.</span></span> <span data-ttu-id="7d970-133">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-133">For example:</span></span>  
  
```  
EmptyString=  
```  
  
 <span data-ttu-id="7d970-134">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]부터 텍스트 파일에서는 `#ifdef`*symbol*... `#endif` 및 `#if !`*symbol*... `#endif` 구문을 사용한 조건부 컴파일을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-134">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], text files support conditional compilation with the `#ifdef`*symbol*... `#endif` and `#if !`*symbol*... `#endif` constructs.</span></span> <span data-ttu-id="7d970-135">그런 다음 [리소스 파일 생성기(Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)와 함께 `/define` 스위치를 하여 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-135">You can then use the `/define` switch with [Resource File Generator (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) to define symbols.</span></span> <span data-ttu-id="7d970-136">각 리소스에는 고유한 `#ifdef`*symbol*... `#endif` 또는 `#if !`*symbol*... `#endif` 구문이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-136">Each resource requires its own `#ifdef`*symbol*... `#endif` or `#if !`*symbol*... `#endif` construct.</span></span> <span data-ttu-id="7d970-137">`#ifdef` 문을 사용하고 *symbol*을 정의하면 연관된 리소스는 .resources 파일에 포함되고, 그렇지 않을 경우 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-137">If you use an `#ifdef` statement and *symbol* is defined, the associated resource is included in the .resources file; otherwise, it is not included.</span></span> <span data-ttu-id="7d970-138">`#if !` 문을 사용하고 *symbol*을 정의하지 않으면 연관된 리소스는 .resources 파일에 포함되고, 그렇지 않을 경우 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-138">If you use an `#if !` statement and *symbol* is not defined, the associated resource is included in the .resources file; otherwise, it is not included.</span></span>  
  
 <span data-ttu-id="7d970-139">텍스트 파일에서 주석은 선택 사항이고 줄 시작 부분에서 세미콜론(;) 또는 파운드 기호(#) 뒤에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-139">Comments are optional in text files and are preceded either by a semicolon (;) or by a pound sign (#) at the beginning of a line.</span></span> <span data-ttu-id="7d970-140">주석이 포함된 줄은 파일의 어느 곳에나 배치될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-140">Lines that contain comments can be placed anywhere in the file.</span></span> <span data-ttu-id="7d970-141">주석은 [리소스 파일 생성기(Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 만든 컴파일된 .resources 파일에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-141">Comments are not included in a compiled .resources file that is created by using [Resource File Generator (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).</span></span>  
  
 <span data-ttu-id="7d970-142">텍스트 파일에 있는 빈 줄은 공백으로 간주하고 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-142">Any blank lines in the text files are considered to be white space and are ignored.</span></span>  
  
 <span data-ttu-id="7d970-143">다음 예제에서는 `OKButton` 및 `CancelButton`이라는 두 개의 문자열 리소스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-143">The following example defines two string resources named `OKButton` and `CancelButton`.</span></span>  
  
```  
#Define resources for buttons in the user interface.  
OKButton=OK  
CancelButton=Cancel  
```  
  
 <span data-ttu-id="7d970-144">텍스트 파일에 중복된 *name*이 포함된 경우 [리소스 파일 생성기(Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)는 경고를 표시하고 두 번째 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-144">If the text file contains duplicate occurrences of *name*, [Resource File Generator (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) displays a warning and ignores the second name.</span></span>  
  
 <span data-ttu-id="7d970-145">*value*에는 줄 바꿈 문자가 포함될 수 없지만 `\n` 같은 C 언어 스타일의 이스케이프 문자를 사용하여 새 줄을 나타내고 `\t`를 사용하여 탭을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-145">*value* cannot contain new line characters, but you can use C language-style escape characters such as `\n` to represent a new line and `\t` to represent a tab.</span></span> <span data-ttu-id="7d970-146">이스케이프된 경우 백슬래시 문자를 포함할 수도 있습니다(예: "\\\\").</span><span class="sxs-lookup"><span data-stu-id="7d970-146">You can also include a backslash character if it is escaped (for example, "\\\\").</span></span> <span data-ttu-id="7d970-147">또한 빈 문자열이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-147">In addition, an empty string is permitted.</span></span>  
  
 <span data-ttu-id="7d970-148">little-endian 또는 big-endian 바이트 순서의 UTF-8 인코딩이나 UTF-16 인코딩을 사용하여 텍스트 파일 형식으로 리소스를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-148">You should save resources in text file format by using UTF-8 encoding or UTF-16 encoding in either little-endian or big-endian byte order.</span></span> <span data-ttu-id="7d970-149">하지만 .txt 파일을 .resources 파일로 변환하는 [리소스 파일 생성기(Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)는 기본적으로 파일을 UTF-8로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-149">However, [Resource File Generator (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md), which converts a .txt file to a .resources file, treats files as UTF-8 by default.</span></span> <span data-ttu-id="7d970-150">Resgen.exe가 UTF-16을 사용하여 인코딩된 파일을 인식하게 하려면 파일 시작 부분에 유니코드 바이트 순서 표시(U+FEFF)를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-150">If you want Resgen.exe to recognize a file that was encoded using UTF-16, you must include a Unicode byte order mark (U+FEFF) at the beginning of the file.</span></span>  
  
 <span data-ttu-id="7d970-151">텍스트 형식의 리소스 파일을 .NET Framework 어셈블리에 포함하려면 [리소스 파일 생성기(Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 파일을 이진 리소스(.resources) 파일로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-151">To embed a resource file in text format into a .NET Framework assembly, you must convert the file to a binary resource (.resources) file by using [Resource File Generator (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md).</span></span> <span data-ttu-id="7d970-152">그 다음에 언어 컴파일러를 사용하여 .resources 파일을 .NET Framework 어셈블리에 포함하거나, [어셈블리 링커(Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-152">You can then embed the .resources file in a .NET Framework assembly by using a language compiler or embed it in a satellite assembly by using [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span>  
  
 <span data-ttu-id="7d970-153">다음 예제에서는 간단한 "Hello World" 콘솔 응용 프로그램에 GreetingResources.txt라는 텍스트 형식의 리소스 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-153">The following example uses a resource file in text format named GreetingResources.txt for a simple "Hello World" console application.</span></span> <span data-ttu-id="7d970-154">텍스트 파일은 사용자에게 이름을 입력하도록 메시지를 표시하고 인사말을 표시하는 두 개의 문자열인 `prompt` 및 `greeting`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-154">The text file defines two strings, `prompt` and `greeting`, that prompt the user to enter his or her name and display a greeting.</span></span>  
  
```  
# GreetingResources.txt   
# A resource file in text format for a "Hello World" application.  
#  
# Initial prompt to the user.  
prompt=Enter your name:   
# Format string to display the result.  
greeting=Hello, {0}!  
```  
  
 <span data-ttu-id="7d970-155">텍스트 파일은 다음 명령을 사용하여 .resources 파일로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-155">The text file is converted to a .resources file by using the following command:</span></span>  
  
 <span data-ttu-id="7d970-156">**resgen GreetingResources.txt**</span><span class="sxs-lookup"><span data-stu-id="7d970-156">**resgen GreetingResources.txt**</span></span>  
  
 <span data-ttu-id="7d970-157">다음 예제에서는 .resources 파일을 사용하여 사용자에게 메시지를 표시하는 콘솔 응용 프로그램에 대한 소스 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-157">The following example shows the source code for a console application that uses the .resources file to display messages to the user.</span></span>  
  
 <span data-ttu-id="7d970-158">[!code-csharp[Conceptual.Resources.TextFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.textfiles/cs/greeting.cs#1)] [!code-vb[Conceptual.Resources.TextFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.textfiles/vb/greeting.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="7d970-158">[!code-csharp[Conceptual.Resources.TextFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.textfiles/cs/greeting.cs#1)] [!code-vb[Conceptual.Resources.TextFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.textfiles/vb/greeting.vb#1)]</span></span>  
  
 <span data-ttu-id="7d970-159">Visual Basic을 사용하고 있고 소스 코드 파일 이름이 Greeting.vb라면 다음 명령은 포함된 .resources 파일을 포함하는 실행 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-159">If you are using Visual Basic, and the source code file is named Greeting.vb, the following command creates an executable file that includes the embedded .resources file:</span></span>  
  
 <span data-ttu-id="7d970-160">**vbc greeting.vb /resource:GreetingResources.resources**</span><span class="sxs-lookup"><span data-stu-id="7d970-160">**vbc greeting.vb /resource:GreetingResources.resources**</span></span>  
  
 <span data-ttu-id="7d970-161">C#을 사용하고 있고 소스 코드 파일 이름이 Greeting.cs라면 다음 명령은 포함된 .resources 파일을 포함하는 실행 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-161">If you are using C#, and the source code file is named Greeting.cs, the following command creates an executable file that includes the embedded .resources file:</span></span>  
  
 <span data-ttu-id="7d970-162">**csc greeting.cs /resource:GreetingResources.resources**</span><span class="sxs-lookup"><span data-stu-id="7d970-162">**csc greeting.cs /resource:GreetingResources.resources**</span></span>  
  
<a name="ResxFiles"></a>   
## <a name="resources-in-resx-files"></a><span data-ttu-id="7d970-163">.resx 파일의 리소스</span><span class="sxs-lookup"><span data-stu-id="7d970-163">Resources in .resx Files</span></span>  
 <span data-ttu-id="7d970-164">문자열 리소스만 저장할 수 있는 텍스트 파일과 달리 XML 리소스(.resx) 파일은 문자열, 이진 데이터(예: 이미지, 아이콘, 오디오 클립) 및 프로그래밍 개체를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-164">Unlike text files, which can only store string resources, XML resource (.resx) files can store strings, binary data such as images, icons, and audio clips, and programmatic objects.</span></span> <span data-ttu-id="7d970-165">.resx 파일에는 리소스 항목의 형식을 설명하고 데이터 구문 분석에 사용되는 XML에 대한 버전 관리 정보를 지정하는 표준 헤더가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-165">A .resx file contains a standard header, which describes the format of the resource entries and specifies the versioning information for the XML that is used to parse the data.</span></span> <span data-ttu-id="7d970-166">리소스 파일 데이터는 XML 헤더를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-166">The resource file data follows the XML header.</span></span> <span data-ttu-id="7d970-167">각 데이터 항목은 `data` 태그에 포함된 이름/값 쌍으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-167">Each data item consists of a name/value pair that is contained in a `data` tag.</span></span> <span data-ttu-id="7d970-168">해당 `name` 특성은 리소스 이름을 정의하고 중첩된 `value` 태그에는 리소스 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-168">Its `name` attribute defines the resource name, and the nested `value` tag contains the resource value.</span></span> <span data-ttu-id="7d970-169">문자열 데이터의 경우 `value` 태그에 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-169">For string data, the `value` tag contains the string.</span></span>  
  
 <span data-ttu-id="7d970-170">예를 들어 다음 `data` 태그는 값이 “Enter your name:”인 `prompt`라는 문자열 리소스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-170">For example, the following `data` tag defines a string resource named `prompt` whose value is "Enter your name:".</span></span>  
  
```xml  
<data name="prompt" xml:space="preserve">  
  <value>Enter your name:</value>  
</data>  
```  
  
> [!WARNING]
>  <span data-ttu-id="7d970-171">암호, 보안이 중요한 정보 또는 개인 데이터를 저장할 때는 리소스 파일을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-171">Do not use resource files to store passwords, security-sensitive information, or private data.</span></span>  
  
 <span data-ttu-id="7d970-172">리소스 개체의 경우 **data** 태그에는 리소스의 데이터 형식을 나타내는 `type` 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-172">For resource objects, the **data** tag includes a `type` attribute that indicates the data type of the resource.</span></span> <span data-ttu-id="7d970-173">이진 데이터로 구성된 개체의 경우 `data` 태그에는 이진 데이터의 `base64` 형식을 나타내는 `mimetype` 특성도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-173">For objects that consist of binary data, the `data` tag also includes a `mimetype` attribute, which indicates the `base64` type of the binary data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d970-174">모든 .resx 파일에는 이진 serialization 포맷터를 사용하여 지정된 형식의 이진 데이터를 생성하고 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-174">All .resx files use a binary serialization formatter to generate and parse the binary data for a specified type.</span></span> <span data-ttu-id="7d970-175">따라서 개체에 대한 이진 serialization 형식이 호환되지 않는 방식으로 변경될 경우 .resx 파일이 유효하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-175">As a result, a .resx file can become invalid if the binary serialization format for an object changes in an incompatible way.</span></span>  
  
 <span data-ttu-id="7d970-176">다음 예제에서는 <xref:System.Int32> 리소스 및 비트맵 이미지를 포함하는 .resx 파일의 일부가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-176">The following example shows a portion of a .resx file that includes an <xref:System.Int32> resource and a bitmap image.</span></span>  
  
```xml  
<data name="i1" type="System.Int32, mscorlib">  
  <value>20</value>  
</data>  
  
<data name="flag" type="System.Drawing.Bitmap, System.Drawing,     
    Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"   
    mimetype="application/x-microsoft.net.object.bytearray.base64">  
  <value>  
    AAEAAAD/////AQAAAAAAAAAMAgAAADtTeX…  
  </value>  
</data>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="7d970-177">.resx 파일은 미리 정의된 형식의 잘 구성된(Well-Formed) XML로 구성되어야 하므로, 특히 .resx 파일에 문자열 이외의 리소스가 포함된 경우에는 .resx 파일을 수동으로 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-177">Because .resx files must consist of well-formed XML in a predefined format, we do not recommend working with .resx files manually, particularly when the .resx files contain resources other than strings.</span></span> <span data-ttu-id="7d970-178">대신, Visual Studio에서는 .resx 파일을 만들고 조작할 수 있는 투명한 인터페이스가 제공됩니다. 자세한 내용은 [Visual Studio의 리소스 파일](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#VSResFiles) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-178">Instead, Visual Studio provides a transparent interface for creating and manipulating .resx files; for more information, see the [Resource Files in Visual Studio](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#VSResFiles) section.</span></span> <span data-ttu-id="7d970-179">프로그래밍 방식으로 .resx 파일을 만들고 조작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-179">You can also create and manipulate .resx files programmatically.</span></span> <span data-ttu-id="7d970-180">자세한 내용은 [프로그래밍 방식으로 .resx 파일 작업](../../../docs/framework/resources/working-with-resx-files-programmatically.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-180">For more information, see [Working with .resx Files Programmatically](../../../docs/framework/resources/working-with-resx-files-programmatically.md).</span></span>  
  
<a name="ResourcesFiles"></a>   
## <a name="resources-in-resources-files"></a><span data-ttu-id="7d970-181">.resources 파일의 리소스</span><span class="sxs-lookup"><span data-stu-id="7d970-181">Resources in .resources Files</span></span>  
 <span data-ttu-id="7d970-182"><xref:System.Resources.ResourceWriter?displayProperty=fullName> 클래스를 사용하여 프로그래밍 방식으로 코드에서 직접 이진 리소스(.resources) 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-182">You can use the <xref:System.Resources.ResourceWriter?displayProperty=fullName> class to programmatically create a binary resource (.resources) file directly from code.</span></span> <span data-ttu-id="7d970-183">[리소스 파일 생성기(Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md)를 사용하여 텍스트 파일 또는 .resx 파일에서 .resources 파일을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-183">You can also use [Resource File Generator (Resgen.exe)](../../../docs/framework/tools/resgen-exe-resource-file-generator.md) to create a .resources file from a text file or a .resx file.</span></span> <span data-ttu-id="7d970-184">.resources 파일에는 문자열 데이터 외에 이진 데이터(바이트 배열) 및 개체 데이터가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-184">The .resources file can contain binary data (byte arrays) and object data in addition to string data.</span></span> <span data-ttu-id="7d970-185">프로그래밍 방식으로 .resources 파일을 만들려면 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-185">Programmatically creating a .resources file requires the following steps:</span></span>  
  
1.  <span data-ttu-id="7d970-186">고유한 파일 이름을 사용하여 <xref:System.Resources.ResourceWriter> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-186">Create a <xref:System.Resources.ResourceWriter> object with a unique file name.</span></span> <span data-ttu-id="7d970-187">파일 이름 또는 파일 스트림을 <xref:System.Resources.ResourceWriter> 클래스 생성자로 지정하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-187">You can do this by specifying either a file name or a file stream to a <xref:System.Resources.ResourceWriter> class constructor.</span></span>  
  
2.  <span data-ttu-id="7d970-188">파일에 추가할 각 명명된 리소스에 대해 <xref:System.Resources.ResourceWriter.AddResource%2A?displayProperty=fullName> 메서드의 오버로드 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-188">Call one of the overloads of the <xref:System.Resources.ResourceWriter.AddResource%2A?displayProperty=fullName> method for each named resource to add to the file.</span></span> <span data-ttu-id="7d970-189">리소스는 문자열, 개체 또는 이진 데이터 컬렉션(바이트 배열)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-189">The resource can be a string, an object, or a collection of binary data (a byte array).</span></span>  
  
3.  <span data-ttu-id="7d970-190"><xref:System.Resources.ResourceWriter.Close%2A?displayProperty=fullName> 메서드를 호출하여 리소스를 파일에 쓰고 <xref:System.Resources.ResourceWriter> 개체를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-190">Call the <xref:System.Resources.ResourceWriter.Close%2A?displayProperty=fullName> method to write the resources to the file and to close the <xref:System.Resources.ResourceWriter> object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d970-191">암호, 보안이 중요한 정보 또는 개인 데이터를 저장할 때는 리소스 파일을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-191">Do not use resource files to store passwords, security-sensitive information, or private data.</span></span>  
  
 <span data-ttu-id="7d970-192">다음 예제에서는 문자열 6개, 아이콘 한 개 및 응용 프로그램 정의 개체 2개(`Automobile` 개체 2개)를 저장하는 CarResources.resources라는 .resources 파일을 프로그래밍 방식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-192">The following example programmatically creates a .resources file named CarResources.resources that stores six strings, an icon, and two application-defined objects (two `Automobile` objects).</span></span> <span data-ttu-id="7d970-193">이 예제에서 정의되고 인스턴스화된 `Automobile` 클래스는 <xref:System.SerializableAttribute> 특성으로 태그가 지정되어 이진 serialization 포맷터를 통해 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-193">Note that the `Automobile` class, which is defined and instantiated in the example, is tagged with the <xref:System.SerializableAttribute> attribute, which allows it to be persisted by the binary serialization formatter.</span></span>  
  
 <span data-ttu-id="7d970-194">[!code-csharp[Conceptual.Resources.Resources#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resources/cs/resources1.cs#1)] [!code-vb[Conceptual.Resources.Resources#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resources/vb/resources1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="7d970-194">[!code-csharp[Conceptual.Resources.Resources#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.resources/cs/resources1.cs#1)] [!code-vb[Conceptual.Resources.Resources#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.resources/vb/resources1.vb#1)]</span></span>  
  
 <span data-ttu-id="7d970-195">.resources 파일을 만든 후 언어 컴파일러의 `/resource` 스위치를 포함하여 런타임 실행 파일 또는 라이브러리에 포함하거나, [어셈블리 링커(Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md)를 사용하여 위성 어셈블리에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-195">After you create the .resources file, you can embed it in a run-time executable or library by including the language compiler's `/resource` switch, or embed it in a satellite assembly by using [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md).</span></span>  
  
<a name="VSResFiles"></a>   
## <a name="resource-files-in-visual-studio"></a><span data-ttu-id="7d970-196">Visual Studio의 리소스 파일</span><span class="sxs-lookup"><span data-stu-id="7d970-196">Resource Files in Visual Studio</span></span>  
 <span data-ttu-id="7d970-197">Visual Studio 프로젝트에 리소스 파일을 추가하면 Visual Studio에서는 프로젝트 디렉터리에 .resx 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-197">When you add a resource file to your Visual Studio project, Visual Studio creates a .resx file in the project directory.</span></span> <span data-ttu-id="7d970-198">Visual Studio에서는 문자열, 이미지 및 이진 개체를 추가할 수 있는 리소스 편집기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-198">Visual Studio provides resource editors that enable you to add strings, images, and binary objects.</span></span> <span data-ttu-id="7d970-199">편집기는 정적 데이터만 처리하도록 디자인되어 있으므로 프로그래밍 개체를 저장하는 데는 사용할 수 없습니다. 프로그래밍 방식으로 개체 데이터를 .resx 파일 또는 .resources 파일에 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-199">Because the editors are designed to handle static data only, they cannot be used to store programmatic objects; you must write object data to either a .resx file or to a .resources file programmatically.</span></span> <span data-ttu-id="7d970-200">자세한 내용은 [프로그래밍 방식으로 .resx 파일 작업](../../../docs/framework/resources/working-with-resx-files-programmatically.md) 항목과 [.resources 파일의 리소스](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResourcesFiles) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d970-200">See the [Working with .resx Files Programmatically](../../../docs/framework/resources/working-with-resx-files-programmatically.md) topic and the [Resources in .resources Files](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md#ResourcesFiles) section for more information.</span></span>  
  
 <span data-ttu-id="7d970-201">지역화된 리소스를 추가할 경우 기본 리소스 파일과 같은 루트 파일 이름을 리소스에 지정해야 하고 파일 이름에서 문화권도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-201">If you are adding localized resources, you should give them the same root file name as the main resource file, and you should also designate their culture in the file name.</span></span> <span data-ttu-id="7d970-202">예를 들어 Resources.resx 리소스 파일을 추가할 경우 Resources.en-US.resx 및 Resources.fr-FR.resx 리소스 파일을 만들어 각각 영어(미국) 및 프랑스어(프랑스) 문화권에 대한 지역화된 리소스를 저장할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-202">For example, if you add a resource file named Resources.resx, you might also create resource files named Resources.en-US.resx and Resources.fr-FR.resx to hold localized resources for the English (United States) and French (France) cultures, respectively.</span></span> <span data-ttu-id="7d970-203">응용 프로그램의 기본 문화권도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-203">You should also designate your application's default culture.</span></span> <span data-ttu-id="7d970-204">이 문화권의 리소스는 특정 문화권에 대한 지역화된 리소스를 찾을 수 없는 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-204">This is the culture whose resources are used if no localized resources for a particular culture can be found.</span></span> <span data-ttu-id="7d970-205">기본 문화권을 지정하려면 Visual Studio의 솔루션 탐색기에서 응용 프로그램을 가리키고, **어셈블리 정보**를 클릭하고, **중립 언어** 목록에서 적절한 언어/문화권을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-205">To specify the default culture, in Solution Explorer in Visual Studio, right-click the project name, point to Application, click **Assembly Information**, and select the appropriate language/culture in the **Neutral language** list.</span></span>  
  
 <span data-ttu-id="7d970-206">컴파일 시간에 Visual Studio에서는 먼저 프로젝트의 .resx 파일을 이진 리소스(.resources) 파일로 변환하고 프로젝트 obj 디렉터리의 하위 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-206">At compile time, Visual Studio first converts the .resx files in a project to binary resource (.resources) files and stores them in a subdirectory of the project's obj directory.</span></span> <span data-ttu-id="7d970-207">Visual Studio에서는 지역화된 리소스가 포함되지 않은 모든 리소스 파일을 프로젝트에서 생성된 주 어셈블리에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-207">Visual Studio embeds any resource files that do not contain localized resources in the main assembly that is generated by the project.</span></span> <span data-ttu-id="7d970-208">리소스 파일에 지역화된 리소스가 포함된 경우 Visual Studio에서는 각 지역화된 문화권에 대한 개별 위성 어셈블리에 리소스 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-208">If any resource files contain localized resources, Visual Studio embeds them in separate satellite assemblies for each localized culture.</span></span> <span data-ttu-id="7d970-209">그다음에 각 위성 어셈블리를 이름이 지역화된 문화권과 일치하는 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-209">It then stores each satellite assembly in a directory whose name corresponds to thelocalized culture.</span></span> <span data-ttu-id="7d970-210">예를 들어 지역화된 영어(미국) 리소스는 en-US 하위 디렉터리의 위성 어셈블리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d970-210">For example, localized English (United States) resources are stored in a satellite assembly in the en-US subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d970-211">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d970-211">See Also</span></span>  
 <span data-ttu-id="7d970-212"><xref:System.Resources></span><span class="sxs-lookup"><span data-stu-id="7d970-212"><xref:System.Resources></span></span>   
 <span data-ttu-id="7d970-213">[데스크톱 앱의 리소스](../../../docs/framework/resources/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d970-213">[Resources in Desktop Apps](../../../docs/framework/resources/index.md) </span></span>  
 [<span data-ttu-id="7d970-214">리소스 패키징 및 배포</span><span class="sxs-lookup"><span data-stu-id="7d970-214">Packaging and Deploying Resources</span></span>](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md)

