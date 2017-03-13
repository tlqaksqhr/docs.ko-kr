---
title: "방법: RTF를 일반 텍스트로 변환(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "문자열 [C#], RTF에서 변환"
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# 방법: RTF를 일반 텍스트로 변환(C# 프로그래밍 가이드)
RTF\(서식 있는 텍스트\)는 운영 체제의 제한 없이 문서를 교환할 수 있도록 1980년대 말에 Microsoft에서 개발한 문서 형식입니다.  Microsoft Word와 WordPad에서 모두 RTF 문서를 읽고 쓸 수 있습니다.  .NET Framework에서는 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용하여 RTF를 지원하고 사용자가 WYSIWIG 방식으로 텍스트에 서식을 적용할 수 있는 워드 프로세서를 만들 수 있습니다.  
  
 또한 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용하면 프로그래밍 방식으로 문서에서 RTF 서식을 제거하여 일반 텍스트로 변환할 수 있습니다.  이와 같은 작업을 수행하기 위해 Windows Form에 이 컨트롤을 포함할 필요는 없습니다.  
  
### 프로젝트에서 RichTextBox 컨트롤을 사용하려면  
  
1.  System.Windows.Forms.dll에 대한 참조를 추가합니다.  
  
2.  `System.Windows.Forms` 네임스페이스에 대한 using 지시문을 추가합니다\(옵션\).  
  
## 예제  
 다음 예제에서는 샘플 RTF 파일을 일반 텍스트 형식으로 변환합니다.  파일이 RTF 서식 \(글꼴 정보 등\), 유니코드 글자와 네 가지 확장된 ASCII 문자가 포함 되어 있습니다.  예제 코드는 파일을 열고, 해당 콘텐츠를 전달는 <xref:System.Windows.Forms.RichTextBox> RTF로 텍스트로 콘텐츠를 검색 하 고, 텍스트를 표시 한 <xref:System.Windows.Forms.MessageBox>, 고 출력 텍스트 파일에 u t F\-8 형식.  
  
 `MessageBox` 고 출력 파일에 다음 텍스트를 포함 합니다.  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
  
```  
  
 [!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]  
  
 RTF 문자는 8비트로 인코딩됩니다.  그러나 사용자가 지정한 코드 페이지의 확장 ASCII 문자와 유니코드 문자를 지정할 수 있습니다.  <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> 속성은 [string](../../../csharp/language-reference/keywords/string.md) 형식이므로 문자는 유니코드 UTF\-16으로 인코딩됩니다.  소스 RTF 문서의 모든 확장 ASCII 문자와 유니코드 문자는 텍스트 출력에서 올바르게 인코딩됩니다.  
  
 하지만 <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> 메서드를 사용하여 디스크에 텍스트를 쓰면 텍스트가 바이트 순서 표시가 없는 UTF\-8로 인코딩됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.RichTextBox?displayProperty=fullName>   
 [문자열](../../../csharp/programming-guide/strings/index.md)