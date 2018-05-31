---
title: '방법: XML 문서 기능 사용(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: d7f1f51040033cf25f7f1aefb04d249e6e028ca3
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472778"
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a><span data-ttu-id="43536-102">방법: XML 문서 기능 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="43536-102">How to: Use the XML Documentation Features (C# Programming Guide)</span></span>
<span data-ttu-id="43536-103">다음 샘플은 문서화된 형식에 대한 기본 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-103">The following sample provides a basic overview of a type that has been documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43536-104">예</span><span class="sxs-lookup"><span data-stu-id="43536-104">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  

<span data-ttu-id="43536-105">이 예제에서는 다음 내용과 같은 내용의 .xml 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-105">The example generates an .xml file with the following contents:</span></span>

```xml  
<?xml version="1.0"?>  
<doc>  
 <assembly>  
 <name>xmlsample</name>  
 </assembly>  
 <members>  
 <member name="T:SomeClass">  
 <summary>  
 Class level summary documentation goes here.</summary>  
 <remarks>  
 Longer comments can be associated with a type or member  
 through the remarks tag</remarks>  
 </member>  
 <member name="F:SomeClass.m_Name">  
 <summary>  
 Store for the name property</summary>  
 </member>  
 <member name="M:SomeClass.#ctor">  
 <summary>The class constructor.</summary>  
 </member>  
 <member name="M:SomeClass.SomeMethod(System.String)">  
 <summary>  
 Description for SomeMethod.</summary>  
 <param name="s"> Parameter description for s goes here</param>  
 <seealso cref="T:System.String">  
 You can use the cref attribute on any tag to reference a type or member  
 and the compiler will check that the reference exists. </seealso>  
 </member>  
 <member name="M:SomeClass.SomeOtherMethod">  
 <summary>  
 Some other method. </summary>  
 <returns>  
 Return results are described through the returns tag.</returns>  
 <seealso cref="M:SomeClass.SomeMethod(System.String)">  
 Notice the use of the cref attribute to reference a specific method </seealso>  
 </member>  
 <member name="M:SomeClass.Main(System.String[])">  
 <summary>  
 The entry point for the application.  
 </summary>  
 <param name="args"> A list of command line arguments</param>  
 </member>  
 <member name="P:SomeClass.Name">  
 <summary>  
 Name property </summary>  
 <value>A value tag is used to describe the property value</value>  
 </member>  
 </members>  
</doc>   
```

## <a name="compiling-the-code"></a><span data-ttu-id="43536-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="43536-106">Compiling the Code</span></span>  
 <span data-ttu-id="43536-107">예제를 컴파일하려면 다음 명령줄을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-107">To compile the example, type the following command line:</span></span>  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 <span data-ttu-id="43536-108">이렇게 하면 TYPE 명령을 사용하거나 브라우저에서 볼 수 있는 XML 파일 XMLsample.xml이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="43536-108">This will create the XML file XMLsample.xml, which you can view in your browser or by using the TYPE command.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="43536-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="43536-109">Robust Programming</span></span>  
 <span data-ttu-id="43536-110">XML 문서는 ///로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-110">XML documentation starts with ///.</span></span> <span data-ttu-id="43536-111">새 프로젝트를 만드는 경우 마법사에서 몇 개의 시작 /// 줄을 자동으로 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="43536-111">When you create a new project, the wizards put some starter /// lines in for you.</span></span> <span data-ttu-id="43536-112">이러한 주석의 처리에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43536-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="43536-113">문서는 잘 구성된 XML이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="43536-114">XML이 잘 구성되지 않은 경우 경고가 생성되고, 문서 파일에 오류가 발생했다는 주석이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="43536-114">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>  
  
-   <span data-ttu-id="43536-115">개발자는 각자 고유한 태그 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43536-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="43536-116">권장 태그 집합이 있습니다([문서 주석에 대한 권장 태그](recommended-tags-for-documentation-comments.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="43536-116">There is a recommended set of tags (see [Recommended tags for documentation comments](recommended-tags-for-documentation-comments.md)).</span></span> <span data-ttu-id="43536-117">권장 태그 중 일부는 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43536-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="43536-118">\<param> 태그는 매개 변수를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="43536-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="43536-119">사용되는 경우 컴파일러는 매개 변수가 있고 모든 매개 변수가 문서에서 설명되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="43536-120">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-120">If the verification failed, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="43536-121">`cref` 특성을 태그에 연결하여 코드 요소에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43536-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="43536-122">컴파일러에서 이 코드 요소가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-122">The compiler will verify that this code element exists.</span></span> <span data-ttu-id="43536-123">확인에 실패하면 컴파일러가 경고를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-123">If the verification failed, the compiler issues a warning.</span></span> <span data-ttu-id="43536-124">컴파일러는 `cref` 특성에 설명된 형식을 찾을 때 모든 `using` 문을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="43536-124">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="43536-125">\<summary> 태그는 Visual Studio 내의 IntelliSense에서 형식 또는 멤버에 대한 추가 정보를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="43536-125">The \<summary> tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="43536-126">XML 파일은 형식 및 멤버에 대한 전체 정보를 제공하지 않습니다(예: 형식 정보가 포함되지 않음).</span><span class="sxs-lookup"><span data-stu-id="43536-126">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="43536-127">형식 또는 멤버에 대한 전체 정보를 가져오려면 실제 형식 또는 멤버에 대한 리플렉션과 함께 문서 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43536-127">To get full information about a type or member, the documentation file must be used together with reflection on the actual type or member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43536-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43536-128">See Also</span></span>  
 [<span data-ttu-id="43536-129">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="43536-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="43536-130">/doc(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="43536-130">/doc (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [<span data-ttu-id="43536-131">XML 문서 주석</span><span class="sxs-lookup"><span data-stu-id="43536-131">XML Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)
