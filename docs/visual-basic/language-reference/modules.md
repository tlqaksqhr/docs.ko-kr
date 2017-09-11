---
title: "모듈 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- modules, Visual Basic
ms.assetid: 370bfc90-e8f2-4942-bdec-9897ce605d31
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 808510c83339e1768dba39f119a2e97ac44f0e4a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="modules-visual-basic"></a><span data-ttu-id="af506-102">모듈(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af506-102">Modules (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="af506-103">문자열 조작, 시스템 정보 가져오기, 파일 및 디렉터리 작업을 수행 수학 계산 수행을 비롯 하 여 코드의 일반적인 작업을 간소화할 수 있도록 하는 몇 가지 모듈을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-103"> provides several modules that enable you to simplify common tasks in your code, including manipulating strings, performing mathematical calculations, getting system information, performing file and directory operations, and so on.</span></span> <span data-ttu-id="af506-104">제공 하는 모듈을 나열 하는 다음 표에서 [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-104">The following table lists the modules provided by [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="af506-105"><xref:Microsoft.VisualBasic.Constants></xref:Microsoft.VisualBasic.Constants></span><span class="sxs-lookup"><span data-stu-id="af506-105"><xref:Microsoft.VisualBasic.Constants></span></span>|<span data-ttu-id="af506-106">기타 상수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-106">Contains miscellaneous constants.</span></span> <span data-ttu-id="af506-107">코드에서 이러한 상수를 어디서 나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af506-107">These constants can be used anywhere in your code.</span></span>|  
|<span data-ttu-id="af506-108"><xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="af506-108"><xref:Microsoft.VisualBasic.ControlChars></span></span>|<span data-ttu-id="af506-109">인쇄 및 표시 텍스트에 대 한 상수 제어 문자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-109">Contains constant control characters for printing and displaying text.</span></span>|  
|<span data-ttu-id="af506-110"><xref:Microsoft.VisualBasic.Conversion></xref:Microsoft.VisualBasic.Conversion></span><span class="sxs-lookup"><span data-stu-id="af506-110"><xref:Microsoft.VisualBasic.Conversion></span></span>|<span data-ttu-id="af506-111">숫자를 문자열로, 문자열을 숫자로, 한 데이터 형식을 다른 형식으로 숫자를 다른 진수로 변환 하는 멤버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-111">Contains members that convert decimal numbers to other bases, numbers to strings, strings to numbers, and one data type to another.</span></span>|  
|<span data-ttu-id="af506-112"><xref:Microsoft.VisualBasic.DateAndTime></xref:Microsoft.VisualBasic.DateAndTime></span><span class="sxs-lookup"><span data-stu-id="af506-112"><xref:Microsoft.VisualBasic.DateAndTime></span></span>|<span data-ttu-id="af506-113">현재 날짜 또는 시간, 날짜 계산을 수행, 날짜 또는 시간 반환, 날짜 또는 시간을 설정 하거나 프로세스의 진행 기간 멤버가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af506-113">Contains members that get the current date or time, perform date calculations, return a date or time, set the date or time, or time the duration of a process.</span></span>|  
|<span data-ttu-id="af506-114"><xref:Microsoft.VisualBasic.ErrObject></xref:Microsoft.VisualBasic.ErrObject></span><span class="sxs-lookup"><span data-stu-id="af506-114"><xref:Microsoft.VisualBasic.ErrObject></span></span>|<span data-ttu-id="af506-115">런타임 오류 및 메서드를 발생 시키거나 오류를 해결 하는 방법에 대 한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af506-115">Contains information about run-time errors and methods to raise or clear an error.</span></span>|  
|<span data-ttu-id="af506-116"><xref:Microsoft.VisualBasic.FileSystem></xref:Microsoft.VisualBasic.FileSystem></span><span class="sxs-lookup"><span data-stu-id="af506-116"><xref:Microsoft.VisualBasic.FileSystem></span></span>|<span data-ttu-id="af506-117">파일, 디렉터리 또는 폴더 및 시스템 작업을 수행 하는 멤버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-117">Contains members that perform file, directory or folder, and system operations.</span></span>|  
|<span data-ttu-id="af506-118"><xref:Microsoft.VisualBasic.Financial></xref:Microsoft.VisualBasic.Financial></span><span class="sxs-lookup"><span data-stu-id="af506-118"><xref:Microsoft.VisualBasic.Financial></span></span>|<span data-ttu-id="af506-119">재무 계산을 수행 하는 데 사용 되는 절차가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af506-119">Contains procedures that are used to perform financial calculations.</span></span>|  
|<span data-ttu-id="af506-120"><xref:Microsoft.VisualBasic.Globals></xref:Microsoft.VisualBasic.Globals></span><span class="sxs-lookup"><span data-stu-id="af506-120"><xref:Microsoft.VisualBasic.Globals></span></span>|<span data-ttu-id="af506-121">현재 스크립팅 엔진 버전에 대 한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-121">Contains information about the current scripting engine version.</span></span>|  
|<span data-ttu-id="af506-122"><xref:Microsoft.VisualBasic.Information></xref:Microsoft.VisualBasic.Information></span><span class="sxs-lookup"><span data-stu-id="af506-122"><xref:Microsoft.VisualBasic.Information></span></span>|<span data-ttu-id="af506-123">반환, 테스트 또는 배열 크기, 형식 이름 등의 정보를 확인 하는 멤버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-123">Contains the members that return, test for, or verify information such as array size, type names, and so on.</span></span>|  
|<span data-ttu-id="af506-124"><xref:Microsoft.VisualBasic.Interaction></xref:Microsoft.VisualBasic.Interaction></span><span class="sxs-lookup"><span data-stu-id="af506-124"><xref:Microsoft.VisualBasic.Interaction></span></span>|<span data-ttu-id="af506-125">포함 개체, 응용 프로그램 및 시스템과 상호 작용 하는 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="af506-125">Contains members interact with objects, applications, and systems.</span></span>|  
|<span data-ttu-id="af506-126"><xref:Microsoft.VisualBasic.Strings></xref:Microsoft.VisualBasic.Strings></span><span class="sxs-lookup"><span data-stu-id="af506-126"><xref:Microsoft.VisualBasic.Strings></span></span>|<span data-ttu-id="af506-127">문자열은 문자열의 길이 가져오는, 문자열 검색 문자열을 다시 포맷 하는 등의 작업을 수행 하는 멤버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-127">Contains members that perform string operations such as reformatting strings, searching a string, getting the length of a string, and so on.</span></span>|  
|<span data-ttu-id="af506-128"><xref:Microsoft.VisualBasic.VBMath></xref:Microsoft.VisualBasic.VBMath></span><span class="sxs-lookup"><span data-stu-id="af506-128"><xref:Microsoft.VisualBasic.VBMath></span></span>|<span data-ttu-id="af506-129">포함 된 멤버에는 수학 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="af506-129">Contains members perform mathematical operations.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af506-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af506-130">See Also</span></span>  
 <span data-ttu-id="af506-131">[Visual Basic 언어 참조](../../visual-basic/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="af506-131">[Visual Basic Language Reference](../../visual-basic/language-reference/index.md) </span></span>  
<span data-ttu-id="af506-132"> [Visual Basic](../../visual-basic/index.md)</span><span class="sxs-lookup"><span data-stu-id="af506-132"> [Visual Basic](../../visual-basic/index.md)</span></span>
