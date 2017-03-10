---
title: "Walkthrough: Encrypting and Decrypting Strings in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "encryption, strings"
  - "strings [Visual Basic], encrypting"
  - "decryption, strings"
  - "strings [Visual Basic], decrypting"
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Walkthrough: Encrypting and Decrypting Strings in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 연습에서는 <xref:System.Security.Cryptography.DESCryptoServiceProvider> 클래스에서 Triple DES\(<xref:System.Security.Cryptography.TripleDES>\) 알고리즘의 CSP\(Cryptographic Service Provider\) 버전을 사용하여 문자열을 암호화하고 해독하는 방법을 보여 줍니다.  첫 번째 단계에서는 3DES 알고리즘을 캡슐화하고 암호화된 데이터를 Base\-64 인코딩된 문자열로 저장하는 간단한 래퍼 클래스를 만듭니다.  그런 다음 해당 래퍼를 사용하여 개인 사용자 데이터를 공개적으로 액세스 가능한 텍스트 파일에 안전하게 저장합니다.  
  
 암호화를 사용하여 사용자 비밀\(예: 암호\)을 보호하고 권한이 없는 사용자가 자격 증명을 읽지 못하게 합니다.  그렇게 하면 권한이 있는 사용자의 ID를 도난으로부터 보호하므로 사용자의 자산을 보호하고 거부 방지 기능을 제공할 수 있습니다.  암호화를 사용하면 사용자 데이터를 권한이 없는 사용자가 액세스하지 못하도록 보호할 수도 있습니다.  
  
 자세한 내용은 [암호화 서비스](../Topic/Cryptographic%20Services.md)을 참조하십시오.  
  
> [!IMPORTANT]
>  Rijndael\(AES\[Advanced Encryption Standard\]\) 및 3DES\(Triple Data Encryption Standard\) 알고리즘을 사용하면 계산이 더 복잡하므로 DES를 사용할 때보다 보안을 강화할 수 있습니다.  자세한 내용은 <xref:System.Security.Cryptography.DES> 및 <xref:System.Security.Cryptography.Rijndael>를 참조하십시오.  
  
### 암호화 래퍼를 만들려면  
  
1.  작성 된 `Simple3Des` 암호화 및 해독 메서드를 캡슐화 하는 클래스입니다.  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/walkthrough-encrypting-a_1.vb)]  
  
2.  암호화 네임 스페이스 가져오기를 추가 포함 된 파일을 시작 하는 `Simple3Des` 클래스입니다.  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/walkthrough-encrypting-a_2.vb)]  
  
3.  에 `Simple3Des` 클래스에서 3DES 암호화 서비스 공급자를 저장할 전용 필드를 추가 합니다.  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/walkthrough-encrypting-a_3.vb)]  
  
4.  지정된 키의 해시로부터 지정된 길이의 바이트 배열을 만드는 전용 메서드를 추가합니다.  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/walkthrough-encrypting-a_4.vb)]  
  
5.  3DES 암호화 서비스 공급자를 초기화할 생성자를 추가합니다.  
  
     `key` 매개 변수는 `EncryptData` 및 `DecryptData` 메서드를 제어합니다.  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/walkthrough-encrypting-a_5.vb)]  
  
6.  문자열을 암호화하는 공용 메서드를 추가합니다.  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/walkthrough-encrypting-a_6.vb)]  
  
7.  문자열을 해독하는 공용 메서드를 추가합니다.  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/walkthrough-encrypting-a_7.vb)]  
  
     래퍼 클래스를 사용하여 사용자 자산을 보호할 수 있습니다.  이 예제에서는 래퍼 클래스를 사용하여 개인 사용자 데이터를 공개적으로 액세스 가능한 텍스트 파일에 안전하게 저장합니다.  
  
### 암호화 래퍼를 테스트하려면  
  
1.  개별 클래스에서 래퍼의 `EncryptData` 메서드를 사용하여 문자열을 암호화한 다음 사용자의 내 문서 폴더에 쓰는 메서드를 추가합니다.  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/walkthrough-encrypting-a_8.vb)]  
  
2.  사용자의 내 문서 폴더에서 암호화된 문자열을 읽은 다음 래퍼의 `DecryptData` 메서드를 사용하여 해독하는 메서드를 추가합니다.  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/walkthrough-encrypting-a_9.vb)]  
  
3.  `TestEncoding` 및 `TestDecoding` 메서드를 호출하는 사용자 인터페이스 코드를 추가합니다.  
  
4.  응용 프로그램을 실행합니다.  
  
     응용 프로그램을 테스트할 때 잘못된 암호를 제공하면 데이터가 해독되지 않습니다.  
  
## 참고 항목  
 <xref:System.Security.Cryptography>   
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>   
 <xref:System.Security.Cryptography.DES>   
 <xref:System.Security.Cryptography.TripleDES>   
 <xref:System.Security.Cryptography.Rijndael>   
 [암호화 서비스](../Topic/Cryptographic%20Services.md)