---
title: "-utf8output(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /utf8output
helpviewer_keywords:
- utf8output compiler option [C#]
- /utf8output compiler option [C#]
- -utf8output compiler option [C#]
ms.assetid: 27ff7381-c281-45d7-b2eb-1ad644b1354e
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 95630afcfcd2ae9ab64660eb0f022dd0733b4c4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="utf8output-c-compiler-options"></a><span data-ttu-id="fd1da-102">/utf8output(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="fd1da-102">/utf8output (C# Compiler Options)</span></span>
<span data-ttu-id="fd1da-103">**/utf8output** 옵션은 UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1da-103">The **/utf8output** option displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd1da-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd1da-104">Syntax</span></span>  
  
```console  
/utf8output  
```  
  
## <a name="remarks"></a><span data-ttu-id="fd1da-105">설명</span><span class="sxs-lookup"><span data-stu-id="fd1da-105">Remarks</span></span>  
 <span data-ttu-id="fd1da-106">일부 국제 구성에서는 컴파일러 출력이 콘솔에 올바르게 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd1da-106">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="fd1da-107">이러한 구성에서는 **/utf8output**을 사용하고 컴파일러 출력을 파일로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="fd1da-107">In these configurations, use **/utf8output** and redirect compiler output to a file.</span></span>  
  
 <span data-ttu-id="fd1da-108">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd1da-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd1da-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd1da-109">See Also</span></span>  
 [<span data-ttu-id="fd1da-110">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="fd1da-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
