---
title: "방법: RTF를 일반 텍스트로 변환(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], converting from RTF
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e4c7b48467f3b260526c604fa3a36fc5d80374e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a>방법: RTF를 일반 텍스트로 변환(C# 프로그래밍 가이드)
RTF(서식 있는 텍스트)는 운영 체제 간에 문서를 교환할 수 있도록 Microsoft에서 1980년대 말에 개발한 문서 형식입니다. Microsoft Word와 WordPad 모두에서 RTF 문서를 읽고 쓸 수 있습니다. .NET Framework에서는 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용하여 RTF를 지원하고 사용자가 WYSIWIG 방식으로 텍스트에 서식을 적용할 수 있도록 하는 워드 프로세서를 만들 수 있습니다.  
  
 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용하여 프로그래밍 방식으로 문서에서 RTF 서식 지정 코드를 제거하고 일반 텍스트로 변환할 수도 있습니다. 이런 종류의 작업을 수행하기 위해 Windows Form에 컨트롤을 포함할 필요가 없습니다.  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a>프로젝트에서 RichTextBox 컨트롤을 사용하려면  
  
1.  System.Windows.Forms.dll에 대한 참조를 추가합니다.  
  
2.  `System.Windows.Forms` 네임스페이스에 대한 using 지시문을 추가합니다(선택 사항).  
  
## <a name="example"></a>예제  
 다음 예제에서는 샘플 RTF 파일을 일반 텍스트로 변환합니다. 파일에는 RTF 서식(예: 글꼴 정보), 유니코드 문자 4자, 확장된 ASCII 문자 4자가 포함되어 있습니다. 예제 코드에서는 파일을 열고 해당 콘텐츠를 <xref:System.Windows.Forms.RichTextBox>에 RTF로 전달하고, 콘텐츠를 텍스트로 검색하고, 텍스트를 <xref:System.Windows.Forms.MessageBox>에 표시하고, 텍스트를 UTF-8 형식의 파일에 출력합니다.  
  
 `MessageBox` 및 출력 파일에는 다음 텍스트가 포함되어 있습니다.  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 [!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]  
  
 RTF 문자는 8비트로 인코드됩니다. 그러나 사용자는 지정된 코드 페이지에서 확장된 ASCII 문자 외에도 유니코드 문자를 지정할 수 있습니다. <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> 속성은 [string](../../../csharp/language-reference/keywords/string.md) 형식이기 때문에 문자가 유니코드 UTF-16으로 인코드됩니다. 소스 RTF 문서의 확장된 ASCII 문자 및 유니코드 문자는 텍스트 출력에 올바르게 인코드됩니다.  
  
 <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> 메서드를 사용하여 디스크에 텍스트를 쓰는 경우 텍스트가 바이트 순서 표시 없이 UTF-8로 인코드됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.RichTextBox?displayProperty=fullName>   
 [문자열](../../../csharp/programming-guide/strings/index.md)

