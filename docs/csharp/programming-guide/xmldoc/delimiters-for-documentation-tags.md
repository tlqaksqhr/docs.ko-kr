---
title: "문서 태그에 대한 구분 기호(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- XML [C#], delimiters
- /** */ delimiters for C# documentation tags
- /// delimiter for C# documentation
ms.assetid: 9b2bdd18-4f5c-4c0b-988e-fb992e0d233e
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a6ab03d220d1ef71605b83c529595dd986ea922a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="delimiters-for-documentation-tags-c-programming-guide"></a><span data-ttu-id="1b64c-102">문서 태그에 대한 구분 기호(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1b64c-102">Delimiters for Documentation Tags (C# Programming Guide)</span></span>
<span data-ttu-id="1b64c-103">XML 문서 주석을 사용하려면 문서 주석이 시작되고 끝나는 위치를 컴파일러에 알리는 구분 기호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-103">The use of XML doc comments requires delimiters, which indicate to the compiler where a documentation comment begins and ends.</span></span> <span data-ttu-id="1b64c-104">XML 문서 태그에 다음과 같은 종류의 구분 기호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-104">You can use the following kinds of delimiters with the XML documentation tags:</span></span>  
  
 `///`  
 <span data-ttu-id="1b64c-105">한 줄 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-105">Single-line delimiter.</span></span> <span data-ttu-id="1b64c-106">문서 예제에 표시되고 Visual C# 프로젝트 템플릿에 사용되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-106">This is the form that is shown in documentation examples and used by the Visual C# project templates.</span></span> <span data-ttu-id="1b64c-107">구분 기호 뒤에 공백 문자가 있으면 해당 문자는 XML 출력에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-107">If there is a white space character following the delimiter, that character is not included in the XML output.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b64c-108">Visual Studio IDE에는 코드 편집기에서 `///` 구분 기호를 입력한 후 \<summary> 및 \</summary> 태그를 자동으로 삽입하고 이러한 태그 내에서 커서를 이동하는 스마트 주석 편집이라는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-108">The Visual Studio IDE has a feature called Smart Comment Editing that automatically inserts the \<summary> and \</summary> tags and moves your cursor within these tags after you type the `///` delimiter in the Code Editor.</span></span> <span data-ttu-id="1b64c-109">이 기능은 프로젝트 속성 페이지의 [옵션, 텍스트 편집기, C#, 서식](/visualstudio/ide/reference/options-text-editor-csharp-formatting)에서 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-109">Access this feature from the [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting) in your project property pages.</span></span>  
  
 `/** */`  
 <span data-ttu-id="1b64c-110">여러 줄 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-110">Multiline delimiters.</span></span>  
  
 <span data-ttu-id="1b64c-111">`/** */` 구분 기호를 사용할 때 따라야 하는 몇 가지 서식 설정 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-111">There are some formatting rules to follow when you use the `/** */` delimiters.</span></span>  
  
-   <span data-ttu-id="1b64c-112">`/**` 구분 기호가 포함된 줄에서 줄의 나머지 부분이 공백인 경우 해당 줄은 주석에 대해 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-112">On the line that contains the `/**` delimiter, if the remainder of the line is white space, the line is not processed for comments.</span></span> <span data-ttu-id="1b64c-113">`/**` 구분 기호 다음의 첫 번째 문자가 공백인 경우 해당 공백 문자는 무시되고 줄의 나머지 부분이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-113">If the first character after the `/**` delimiter is white space, that white space character is ignored and the rest of the line is processed.</span></span> <span data-ttu-id="1b64c-114">그러지 않으면 `/**` 구분 기호 다음 줄의 전체 텍스트가 주석의 일부로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-114">Otherwise, the entire text of the line after the `/**` delimiter is processed as part of the comment.</span></span>  
  
-   <span data-ttu-id="1b64c-115">`*/` 구분 기호가 포함된 줄에서 `*/` 구분 기호까지 공백만 있으면 해당 줄은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-115">On the line that contains the `*/` delimiter, if there is only white space up to the `*/` delimiter, that line is ignored.</span></span> <span data-ttu-id="1b64c-116">그러지 않으면 줄의 텍스트가 `*/` 구분 기호까지 주석의 일부로 처리되며, 다음 글머리 기호에서 설명하는 패턴 일치 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-116">Otherwise, the text on the line up to the `*/` delimiter is processed as part of the comment, subject to the pattern-matching rules described in the following bullet.</span></span>  
  
-   <span data-ttu-id="1b64c-117">`/**` 구분 기호로 시작하는 줄 다음 줄에 대해 컴파일러는 각 줄의 시작 부분에서 일반적인 패턴을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-117">For the lines after the one that begins with the `/**` delimiter, the compiler looks for a common pattern at the beginning of each line.</span></span> <span data-ttu-id="1b64c-118">패턴은 선택적 공백과 별표(`*`)로 구성되고 그다음에 더 많은 선택적 공백이 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-118">The pattern can consist of optional white space and an asterisk (`*`), followed by more optional white space.</span></span> <span data-ttu-id="1b64c-119">컴파일러가 `/**` 구분 기호나 `*/` 구분 기호로 시작되지 않는 각 줄의 시작 부분에서 일반적인 패턴을 찾으면 각 줄에 대해 해당 패턴을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-119">If the compiler finds a common pattern at the beginning of each line that does not begin with the `/**` delimiter or the `*/` delimiter, it ignores that pattern for each line.</span></span>  
  
 <span data-ttu-id="1b64c-120">다음 예제에서는 이러한 규칙을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-120">The following examples illustrate these rules.</span></span>  
  
-   <span data-ttu-id="1b64c-121">다음 주석에서 유일하게 처리되는 부분은 `<summary>`로 시작하는 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-121">The only part of the following comment that will be processed is the line that begins with `<summary>`.</span></span> <span data-ttu-id="1b64c-122">세 가지 태그 서식이 동일한 주석을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-122">The three tag formats produce the same comments.</span></span>  
  
    ```  
    /** <summary>text</summary> */   
  
    /**   
    <summary>text</summary>   
    */   
  
    /**   
     * <summary>text</summary>   
    */  
    ```  
  
-   <span data-ttu-id="1b64c-123">컴파일러는 두 번째 및 세 번째 줄의 시작 부분에서 " * "의 일반적인 패턴을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-123">The compiler identifies a common pattern of " * " at the beginning of the second and third lines.</span></span> <span data-ttu-id="1b64c-124">이 패턴은 출력에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-124">The pattern is not included in the output.</span></span>  
  
    ```  
    /**   
     * <summary>   
     * text </summary>*/   
    ```  
  
-   <span data-ttu-id="1b64c-125">다음 주석에서는 세 번째 줄의 두 번째 문자가 별표가 아니기 때문에 컴파일러가 일반적인 패턴을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-125">The compiler finds no common pattern in the following comment because the second character on the third line is not an asterisk.</span></span> <span data-ttu-id="1b64c-126">따라서 두 번째 및 세 번째 줄의 모든 텍스트가 주석의 일부로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-126">Therefore, all text on the second and third lines is processed as part of the comment.</span></span>  
  
    ```  
    /**   
     * <summary>   
       text </summary>  
    */   
    ```  
  
-   <span data-ttu-id="1b64c-127">다음 주석에서는 두 가지로 이유로 컴파일러가 패턴을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-127">The compiler finds no pattern in the following comment for two reasons.</span></span> <span data-ttu-id="1b64c-128">첫째, 별표 앞의 공백 수가 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-128">First, the number of spaces before the asterisk is not consistent.</span></span> <span data-ttu-id="1b64c-129">둘째, 다섯 번째 줄이 공백과 일치하지 않는 탭으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-129">Second, the fifth line begins with a tab, which does not match spaces.</span></span> <span data-ttu-id="1b64c-130">따라서 두 번째 줄부터 다섯 번째 줄까지 모든 텍스트가 주석의 일부로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b64c-130">Therefore, all text from lines two through five is processed as part of the comment.</span></span>  
  
    ```  
    /**   
      * <summary>   
      * text   
     *  text2   
        *  </summary>   
    */   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b64c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b64c-131">See Also</span></span>  
 [<span data-ttu-id="1b64c-132">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1b64c-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1b64c-133">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="1b64c-133">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)  
 [<span data-ttu-id="1b64c-134">/doc (C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="1b64c-134">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="1b64c-135">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="1b64c-135">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
