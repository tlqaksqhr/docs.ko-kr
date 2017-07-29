---
title: "방법: StreamReader를 사용하여 파일에서 텍스트 읽기(Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- reading files, text
- text, reading from files
- reading text from files
- files, reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
caps.latest.revision: 18
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d895b32b1613462a6c8dedcc19040b5040f936ec
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a>방법: StreamReader를 사용하여 파일에서 텍스트 읽기(Visual Basic)
`My.Computer.FileSystem` 개체는 <xref:System.IO.TextReader> 및 <xref:System.IO.TextWriter>를 여는 메서드를 제공합니다. `OpenTextFileWriter` 및 `OpenTextFileReader` 메서드는 **모두** 탭을 선택한 경우에만 IntelliSense에 표시되는 고급 메서드입니다.  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a>텍스트 판독기를 사용하여 파일에서 줄을 읽으려면  
  
-   파일을 지정하여 `OpenTextFileReader` 메서드를 통해 <xref:System.IO.TextReader>를 엽니다. 이 예제에서는 `testfile.txt`라는 파일을 열고 파일에서 줄을 읽은 다음 메시지 상자에 줄을 표시합니다.  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 읽은 파일은 텍스트 파일이어야 합니다.  
  
 파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다. 예를 들어 Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.  
  
 응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다. 파일의 내용이 예상한 내용과 다를 수 있으며 파일을 읽는 메서드가 실패할 수도 있습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 파일에서 읽으려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermission> 클래스에서 부여한 권한 수준이 필요합니다. 부분 신뢰 컨텍스트에서 실행하는 경우 권한 부족으로 인해 코드에서 예외를 throw할 수 있습니다. 자세한 내용은 [코드 액세스 보안 기본 사항](https://msdn.microsoft.com/library/33tceax8)을 참조하세요. 사용자에게 파일에 대한 액세스 권한도 필요합니다. 자세한 내용은 [ACL 기술 개요](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:System.Windows.Forms.OpenFileDialog>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>   
 [SaveFileDialog 구성 요소](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)   
 [파일 읽기](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)

