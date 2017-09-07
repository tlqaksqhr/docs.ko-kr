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
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a>방법: 레거시 인코딩과 유니코드 간 변환(C# 프로그래밍 가이드)
C#에서는 메모리에 있는 모든 문자열이 유니코드(UTF-16)로 인코드됩니다. 저장소의 데이터를 `string` 개체로 가져오면 데이터가 자동으로 UTF-16으로 변환됩니다. 데이터에 0에서 127 사이의 ASCII 값만 포함된 경우 변환을 위해 별도의 추가 작업이 필요 없습니다. 그러나 소스 텍스트에 확장된 ASCII 바이트 값(128-255)이 포함된 경우에는 확장된 문자가 기본적으로 현재 코드 페이지에 따라 해석됩니다. 소스 텍스트가 다른 코드 페이지에 따라 해석되도록 지정하려면 다음 예제와 같이 <xref:System.Text.Encoding?displayProperty=fullName> 클래스를 사용합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 Windows 코드 페이지 737에 따라 소스 텍스트를 해석하여 8비트 ASCII로 인코드된 텍스트 파일을 변환하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [문자열](../../../csharp/programming-guide/strings/index.md)

