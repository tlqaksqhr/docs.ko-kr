---
title: /linkresource(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /linkresource compiler option [Visual Basic]
- -linkresource compiler option [Visual Basic]
- linkresource compiler option [Visual Basic]
- /linkres compiler option [Visual Basic]
- linkres compiler option [Visual Basic]
- -linkres compiler option [Visual Basic]
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e51f844695985485210a1e4bedfef7ac968326c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="linkresource-visual-basic"></a><span data-ttu-id="56dc4-102">/linkresource(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56dc4-102">/linkresource (Visual Basic)</span></span>
<span data-ttu-id="56dc4-103">관리되는 리소스에 대한 링크를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-103">Creates a link to a managed resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56dc4-104">구문</span><span class="sxs-lookup"><span data-stu-id="56dc4-104">Syntax</span></span>  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="56dc4-105">인수</span><span class="sxs-lookup"><span data-stu-id="56dc4-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="56dc4-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="56dc4-106">Required.</span></span> <span data-ttu-id="56dc4-107">어셈블리에 연결할 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-107">The resource file to link to the assembly.</span></span> <span data-ttu-id="56dc4-108">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다 ("").</span><span class="sxs-lookup"><span data-stu-id="56dc4-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
 `identifier`  
 <span data-ttu-id="56dc4-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-109">Optional.</span></span> <span data-ttu-id="56dc4-110">리소스에 대 한 논리적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-110">The logical name for the resource.</span></span> <span data-ttu-id="56dc4-111">리소스를 로드 하는 데 사용 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-111">The name that is used to load the resource.</span></span> <span data-ttu-id="56dc4-112">기본값은 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-112">The default is the name of the file.</span></span> <span data-ttu-id="56dc4-113">파일 인지 공개 또는 개인 어셈블리 매니페스트에 예를 들어 지정할 수 있습니다: `/linkres:filename.res,myname.res,public`합니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-113">Optionally, you can specify whether the file is public or private in the assembly manifest, for example: `/linkres:filename.res,myname.res,public`.</span></span> <span data-ttu-id="56dc4-114">기본적으로 `filename` 어셈블리에 공개 합니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-114">By default, `filename` is public in the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56dc4-115">설명</span><span class="sxs-lookup"><span data-stu-id="56dc4-115">Remarks</span></span>  
 <span data-ttu-id="56dc4-116">`/linkresource` 옵션은 출력 파일에 리소스 파일을 포함 하지 않습니다; 사용 된 `/resource` 이 작업을 수행 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-116">The `/linkresource` option does not embed the resource file in the output file; use the `/resource` option to do this.</span></span>  
  
 <span data-ttu-id="56dc4-117">`/linkresource` 옵션 중 하나 필요로 `/target` 옵션 이외의 `/target:module`합니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-117">The `/linkresource` option requires one of the `/target` options other than `/target:module`.</span></span>  
  
 <span data-ttu-id="56dc4-118">경우 `filename` 는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 만들어진 리소스 파일, 예를 들어 여는 [Resgen.exe (리소스 파일 생성기)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) 또는 개발 환경에서의 멤버와 액세스할 수 있습니다는 <xref:System.Resources> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-118">If `filename` is a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file created, for example, by the [Resgen.exe (Resource File Generator)](http://msdn.microsoft.com/library/8ef159de-b660-4bec-9213-c3fbc4d1c6f4) or in the development environment, it can be accessed with members in the <xref:System.Resources> namespace.</span></span> <span data-ttu-id="56dc4-119">자세한 내용은 <xref:System.Resources.ResourceManager>을 참조하세요. 로 시작 하는 메서드를 사용 하 여 런타임 시 다른 모든 리소스에 액세스 하려면 `GetManifestResource` 에 <xref:System.Reflection.Assembly> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-119">(For more information, see <xref:System.Resources.ResourceManager>.) To access all other resources at run time, use the methods that begin with `GetManifestResource` in the <xref:System.Reflection.Assembly> class.</span></span>  
  
 <span data-ttu-id="56dc4-120">모든 파일 형식 파일 이름일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-120">The file name can be any file format.</span></span> <span data-ttu-id="56dc4-121">예를 들어 네이티브 DLL을 어셈블리의 일부로 설정하면 전역 어셈블리 캐시에 설치하고 어셈블리의 관리 코드에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-121">For example, you may want to make a native DLL part of the assembly, so that it can be installed into the global assembly cache and accessed from managed code in the assembly.</span></span>  
  
 <span data-ttu-id="56dc4-122">`/linkresource`의 약식은 `/linkres`입니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-122">The short form of `/linkresource` is `/linkres`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56dc4-123">`/linkresource` 옵션은 Visual Studio 개발 환경에서 사용할 수 없습니다; 가능 하다는 명령줄에서 컴파일할 때만 합니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-123">The `/linkresource` option is not available from the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56dc4-124">예제</span><span class="sxs-lookup"><span data-stu-id="56dc4-124">Example</span></span>  
 <span data-ttu-id="56dc4-125">다음 코드에서는 `In.vb` 리소스 파일에 대 한 링크 `Rf.resource`합니다.</span><span class="sxs-lookup"><span data-stu-id="56dc4-125">The following code compiles `In.vb` and links to resource file `Rf.resource`.</span></span>  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="56dc4-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56dc4-126">See Also</span></span>  
 [<span data-ttu-id="56dc4-127">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="56dc4-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="56dc4-128">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56dc4-128">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="56dc4-129">/resource (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56dc4-129">/resource (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)  
 [<span data-ttu-id="56dc4-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="56dc4-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
