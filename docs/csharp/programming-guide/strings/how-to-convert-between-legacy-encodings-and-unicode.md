---
title: "방법: 레거시 인코딩과 유니코드 간 변환(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], legacy to unicode encoding
- strings [C#], converting between encodings
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
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
ms.openlocfilehash: a016f4ab7de25eec408243cb9b467f9255556bba
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a><span data-ttu-id="05123-102">방법: 레거시 인코딩과 유니코드 간 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="05123-102">How to: Convert Between Legacy Encodings and Unicode (C# Programming Guide)</span></span>
<span data-ttu-id="05123-103">C#에서는 메모리에 있는 모든 문자열이 유니코드(UTF-16)로 인코드됩니다.</span><span class="sxs-lookup"><span data-stu-id="05123-103">In C#, all strings in memory are encoded as Unicode (UTF-16).</span></span> <span data-ttu-id="05123-104">저장소의 데이터를 `string` 개체로 가져오면 데이터가 자동으로 UTF-16으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="05123-104">When you bring data from storage into a `string` object, the data is automatically converted to UTF-16.</span></span> <span data-ttu-id="05123-105">데이터에 0에서 127 사이의 ASCII 값만 포함된 경우 변환을 위해 별도의 추가 작업이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05123-105">If the data contains only ASCII values from 0 through 127, the conversion requires no extra effort on your part.</span></span> <span data-ttu-id="05123-106">그러나 소스 텍스트에 확장된 ASCII 바이트 값(128-255)이 포함된 경우에는 확장된 문자가 기본적으로 현재 코드 페이지에 따라 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="05123-106">However, if the source text contains extended ASCII byte values (128 through 255), the extended characters will be interpreted by default according to the current code page.</span></span> <span data-ttu-id="05123-107">소스 텍스트가 다른 코드 페이지에 따라 해석되도록 지정하려면 다음 예제와 같이 <xref:System.Text.Encoding?displayProperty=fullName> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05123-107">To specify that the source text should be interpreted according to a different code page, use the <xref:System.Text.Encoding?displayProperty=fullName> class as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05123-108">예제</span><span class="sxs-lookup"><span data-stu-id="05123-108">Example</span></span>  
 <span data-ttu-id="05123-109">다음 예제에서는 Windows 코드 페이지 737에 따라 소스 텍스트를 해석하여 8비트 ASCII로 인코드된 텍스트 파일을 변환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05123-109">The following example shows how to convert a text file that has been encoded in 8-bit ASCII, interpreting the source text according to Windows Code Page 737.</span></span>  
  
 <span data-ttu-id="05123-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="05123-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05123-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05123-111">See Also</span></span>  
 [<span data-ttu-id="05123-112">문자열</span><span class="sxs-lookup"><span data-stu-id="05123-112">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

