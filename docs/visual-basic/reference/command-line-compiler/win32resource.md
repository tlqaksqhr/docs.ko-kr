---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac495e10be2ec1534dc9d9081aef369773d93e17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649876"
---
# <a name="-win32resource"></a><span data-ttu-id="647ab-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="647ab-102">-win32resource</span></span>
<span data-ttu-id="647ab-103">출력 파일에 Win32 리소스 파일을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="647ab-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="647ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="647ab-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="647ab-105">인수</span><span class="sxs-lookup"><span data-stu-id="647ab-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="647ab-106">출력 파일에 추가 하는 리소스 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="647ab-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="647ab-107">파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="647ab-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="647ab-108">설명</span><span class="sxs-lookup"><span data-stu-id="647ab-108">Remarks</span></span>  
 <span data-ttu-id="647ab-109">Microsoft Windows 리소스 컴파일러 (RC)와 Win32 리소스 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="647ab-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="647ab-110">Win32 리소스 버전을 포함할 수 있습니다 또는에서 응용 프로그램을 식별 하는 데 도움이 되는 비트맵 (아이콘) 정보 **파일 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="647ab-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="647ab-111">지정 하지 않으면 `-win32resource`, 컴파일러는 어셈블리 버전에 따라 버전 정보를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="647ab-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="647ab-112">`-win32resource` 및 `-win32icon` 옵션은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="647ab-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="647ab-113">참조 [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) 참조에는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 리소스 파일 또는 [-리소스 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) 연결할는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 리소스 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="647ab-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="647ab-114">`-win32resource` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="647ab-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="647ab-115">예제</span><span class="sxs-lookup"><span data-stu-id="647ab-115">Example</span></span>  
 <span data-ttu-id="647ab-116">다음 코드에서는 `In.vb` Win32 리소스 파일을 첨부 `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="647ab-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="647ab-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="647ab-117">See Also</span></span>  
 [<span data-ttu-id="647ab-118">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="647ab-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="647ab-119">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="647ab-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
