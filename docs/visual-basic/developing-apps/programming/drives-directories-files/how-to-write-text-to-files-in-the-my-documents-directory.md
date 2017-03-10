---
title: "How to: Write Text to Files in the My Documents Directory in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "files, writing to"
  - "text, writing to files"
  - "examples [Visual Basic], text files"
  - "writing to files, in My Documents"
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Write Text to Files in the My Documents Directory in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Computer.FileSystem.SpecialDirectories` 개체를 사용하면 **MyDocuments** 디렉터리와 같은 특수 디렉터리에 액세스할 수 있습니다.  
  
## 절차  
  
#### 내 문서 디렉터리에 새 텍스트 파일을 쓰려면  
  
1.  `My.Computer.FileSystem.SpecialDirectories.MyDocuments` 속성을 사용하여 경로를 지정합니다.  
  
     [!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-fil_1_1.vb)]  
  
2.  `WriteAllText` 메서드를 사용하여 지정된 파일에 텍스트를 씁니다.  
  
     [!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-fil_1_2.vb)]  
  
## 예제  
 [!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-fil_1_3.vb)]  
  
## 코드 컴파일  
 `test.txt`를 쓰고자 하는 파일의 이름으로 바꿉니다.  
  
## 강력한 프로그래밍  
 이 코드에서는 파일에 텍스트를 쓸 때 발생할 수 있는 모든 예외를 다시 throw합니다.  사용자가 유효한 파일 이름을 선택하도록 제한하는 [OpenFileDialog](../Topic/OpenFileDialog%20Component%20\(Windows%20Forms\).md) 및 [SaveFileDialog](../Topic/SaveFileDialog%20Component%20\(Windows%20Forms\).md) 구성 요소와 같은 Windows Forms 컨트롤을 사용하면 예외가 발생할 가능성을 줄일 수 있습니다.  하지만 이러한 컨트롤을 사용한다고 해서 예외가 발생하지 않는 것은 아닙니다.  사용자가 파일을 선택한 시간과 코드가 실행되는 시간 사이에 파일 시스템이 변경될 수 있기 때문입니다.  따라서 파일로 작업할 때는 거의 항상 예외 처리가 필요합니다.  
  
## .NET Framework 보안  
 부분 신뢰 컨텍스트에서 실행 중인 경우에는 불충분한 권한 때문에 코드에서 예외를 throw할 수 있습니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../Topic/Code%20Access%20Security%20Basics.md)을 참조하십시오.  
  
 이 예제에서는 새 파일을 만듭니다.  응용 프로그램에서 파일을 만들어야 하는 경우 해당 응용 프로그램에는 폴더에 대해 Create 권한이 필요합니다.  사용 권한은 액세스 제어 목록을 사용하여 설정됩니다.  해당 파일이 이미 있으면 응용 프로그램에는 더 낮은 수준의 권한인 Write 권한만 있으면 됩니다.  가능하다면, 배포할 때 파일을 만든 다음 폴더에 대한 Create 권한을 부여하는 것보다는 파일 하나에 대한 Read 권한만을 부여하는 것이 더 안전합니다.  또한 루트 폴더나 **Program Files** 폴더보다 사용자 폴더에 데이터를 쓰는 것이 안전합니다.  자세한 내용은 [ACL Technology Overview](http://msdn.microsoft.com/ko-kr/06fbf66d-6f02-4378-b863-b2f12e349045)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.IO.Path.Combine%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>