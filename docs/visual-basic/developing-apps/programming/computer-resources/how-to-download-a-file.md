---
title: "How to: Download a File in Visual Basic | Microsoft Docs"
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
  - "downloading Internet resources, files"
  - "downloading files"
  - "remote computers, downloading from"
  - "files, downloading"
  - "files, transferring"
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# How to: Download a File in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> 메서드를 사용하여 원격 파일을 다운로드하고 특정 위치에 저장할 수 있습니다.  `ShowUI` 매개 변수가 `True`로 설정된 경우 다운로드 진행률이 표시되고 사용자가 작업을 취소할 수 있는 대화 상자가 표시됩니다.  기본적으로 이름이 같은 기존 파일을 덮어쓰지 않지만, 기존 파일을 덮어쓰려면 `overwrite` 매개 변수를 `True`로 설정합니다.  
  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   드라이브 이름이 잘못된 경우\(<xref:System.ArgumentException>\)  
  
-   필요한 인증을 제공하지 않은 경우\(<xref:System.UnauthorizedAccessException> 또는 <xref:System.Security.SecurityException>\)  
  
-   지정된 `connectionTimeout` 내에 서버가 응답하지 않는 경우\(<xref:System.TimeoutException>\)  
  
-   웹 사이트에서 요청을 거부한 경우\(<xref:System.Net.WebException>\)  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
> [!IMPORTANT]
>  파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.  예를 들어, Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.  응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.  파일의 내용이 예상한 내용과 다를 수 있으며 파일을 읽는 메서드가 실패할 수도 있습니다.  
  
### 파일을 다운로드하려면  
  
-   `DownloadFile` 메서드를 사용하여 대상 파일의 위치를 문자열이나 URI로 지정하고 파일을 저장할 위치를 지정하여 파일을 다운로드합니다.  이 예제에서는 `http://www.cohowinery.com/downloads`에서 `WineList.txt` 파일을 다운로드하여 `C:\Documents and Settings\All Users\Documents`에 저장합니다.  
  
     [!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-download-a-file_1.vb)]  
  
### 시간 제한 간격을 지정하여 파일을 다운로드하려면  
  
-   `DownloadFile` 메서드를 사용하여 대상 파일의 위치를 문자열이나 URI로 지정하고, 파일을 저장할 위치를 지정하고, 시간 제한 간격을 밀리초 단위\(기본값: 1000\)로 지정하여 파일을 다운로드합니다.  이 예제에서는 `http://www.cohowinery.com/downloads`에서 `WineList.txt` 파일을 다운로드하여 `C:\Documents and Settings\All Users\Documents`에 저장하며 시간 제한 간격을 500밀리초로 지정합니다.  
  
     [!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-download-a-file_2.vb)]  
  
### 사용자 이름과 암호를 지정하여 파일을 다운로드하려면  
  
-   `DownLoadFile` 메서드를 사용하여 대상 파일의 위치를 문자열이나 URI로 지정하고 파일을 저장할 위치, 사용자 이름 및 암호를 지정하여 파일을 다운로드합니다.  이 예제에서는 사용자 이름 `anonymous`와 빈 암호를 사용하여 `http://www.cohowinery.com/downloads`에서 `WineList.txt` 파일을 다운로드하여 `C:\Documents and Settings\All Users\Documents`에 저장합니다.  
  
     [!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-download-a-file_3.vb)]  
  
    > [!IMPORTANT]
    >  `DownLoadFile` 메서드에서 사용하는 FTP 프로토콜은 암호 등의 정보를 일반 텍스트로 보내므로 중요한 정보를 전송할 때는 사용하지 말아야 합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Network>   
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>   
 [How to: Upload a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)   
 [방법: 파일 경로의 구문 분석](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)