---
title: "How to: Upload a File in Visual Basic | Microsoft Docs"
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
  - "networks, uploading files"
  - "files, uploading"
  - "uploading files"
  - "UploadFile method"
  - "My.Computer.Network.UploadFile method"
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# How to: Upload a File in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> 메서드를 사용하여 파일을 업로드하고 원격 위치에 저장할 수 있습니다.  `ShowUI` 매개 변수가 `True`로 설정된 경우 다운로드 진행률이 표시되는 대화 상자가 표시되며 사용자가 작업을 취소할 수 있습니다.  
  
### 파일을 업로드하려면  
  
-   `UploadFile` 메서드를 사용하여 소스 파일의 위치와 대상 디렉터리 위치를 문자열 또는 URI\(Uniform Resource Identifier\)로 지정하여 파일을 업로드합니다. 이 예제에서는 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드합니다.  
  
     [!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]  
  
### 파일을 업로드하고 작업 진행률을 표시하려면  
  
-   `UploadFile` 메서드를 사용하여 소스 파일의 위치와 대상 디렉터리 위치를 문자열 또는 URI로 지정하여 파일을 업로드합니다.  이 예제에서는 사용자 이름이나 암호를 지정하지 않고 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드하고, 업로드 진행률을 표시하며, 시간 제한 간격을 500밀리초로 지정합니다.  
  
     [!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]  
  
### 사용자 이름과 암호를 지정하여 파일을 업로드하려면  
  
-   `UploadFile` 메서드를 사용하여 소스 파일의 위치와 대상 디렉터리 위치를 문자열 또는 URI로 지정하고 사용자 이름과 암호를 지정하여 파일을 업로드합니다.  이 예제에서는 사용자 이름 `anonymous`와 빈 암호를 지정하여 `Order.txt` 파일을 `http://www.cohowinery.com/uploads.aspx`에 업로드합니다.  
  
     [!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 throw될 수 있습니다.  
  
-   로컬 파일 경로가 잘못된 경우\(<xref:System.ArgumentException>\)  
  
-   인증이 실패한 경우\(<xref:System.Security.SecurityException>\)  
  
-   연결 시간이 초과된 경우\(<xref:System.TimeoutException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>   
 [How to: Download a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)   
 [방법: 파일 경로의 구문 분석](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)