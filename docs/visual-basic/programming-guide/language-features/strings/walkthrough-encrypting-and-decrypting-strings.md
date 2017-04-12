---
title: "암호화 하 고 Visual Basic에서 문자열을 해독 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- encryption, strings
- strings [Visual Basic], encrypting
- decryption, strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ae3d599f7173162c07fbaeda60435615f101b10d
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>연습: Visual Basic에서 문자열 암호화 및 암호 해독
이 연습에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Security.Cryptography.DESCryptoServiceProvider>암호화 및 Triple Data Encryption Standard의 암호화 서비스 공급자 (CSP) 버전을 사용 하 여 문자열을 해독 하는 클래스 (<xref:System.Security.Cryptography.TripleDES>) 알고리즘.</xref:System.Security.Cryptography.TripleDES> </xref:System.Security.Cryptography.DESCryptoServiceProvider> 첫 번째 단계 3DES 알고리즘을 캡슐화 하 고 base 64로 인코딩된 문자열로 암호화 된 데이터를 저장 하는 간단한 래퍼 클래스를 만드는 것입니다. 그런 다음이 래퍼는 공개적으로 액세스할 수 있는 텍스트 파일에 개인 사용자 데이터를 안전 하 게 저장 하는 데 사용 됩니다.  
  
 사용자의 비밀 (예: 암호)를 보호 하 고 자격 증명을 권한이 없는 사용자가 읽을 수 있도록 암호화를 사용할 수 있습니다. 이 권한이 있는 사용자의 id가 도난 으로부터 사용자의 자산을 보호 하 고 부인 방지 제공 보호할 수 있습니다. 암호화는 권한이 없는 사용자가 액세스 사용자의 데이터를 보호할 수도 있습니다.  
  
 자세한 내용은 참조 [암호화 서비스](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)합니다.  
  
> [!IMPORTANT]
>  Rijndael (현재 이라고 고급 암호화 표준 [AES]) 및 데이터 암호화&3;DES (Triple Standard) 알고리즘 제공 DES 보다 강력한 보안 자세한 있기 때문에 계산을 많이 수행 합니다. 자세한 내용은 <xref:System.Security.Cryptography.DES>및 <xref:System.Security.Cryptography.Rijndael>.</xref:System.Security.Cryptography.Rijndael> </xref:System.Security.Cryptography.DES> 를 참조 하십시오.  
  
### <a name="to-create-the-encryption-wrapper"></a>암호화 래퍼를 만들려면  
  
1.  만들기는 `Simple3Des` 암호화 및 해독 메서드를 캡슐화 하는 클래스입니다.  
  
     [!code-vb[VbVbalrStrings #&38;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  암호화 네임 스페이스 가져오기를 포함 하는 파일의 시작 부분에 추가 된 `Simple3Des` 클래스입니다.  
  
     [!code-vb[VbVbalrStrings #&77;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  에 `Simple3Des` 클래스, 3DES 암호화 서비스 공급자를 저장 하는 개인 필드를 추가 합니다.  
  
     [!code-vb[VbVbalrStrings #&39;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  지정 된 길이의 바이트 배열에서 지정된 된 키의 해시 만드는 개인 메서드를 추가 합니다.  
  
     [!code-vb[VbVbalrStrings #&41;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  3DES 암호화 서비스 공급자를 초기화 하는 생성자를 추가 합니다.  
  
     `key` 매개 변수는 `EncryptData` 및 `DecryptData` 메서드.  
  
     [!code-vb[VbVbalrStrings #&40;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  문자열을 암호화 하는 공용 메서드를 추가 합니다.  
  
     [!code-vb[VbVbalrStrings #&42;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  문자열을 해독 하는 공용 메서드를 추가 합니다.  
  
     [!code-vb[VbVbalrStrings #&43;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     이제 래퍼 클래스를 사용 하 사용자 자산을 보호할 수 있습니다. 이 예제에서는 공개적으로 액세스할 수 있는 텍스트 파일에 개인 사용자 데이터를 안전 하 게 저장에 사용 됩니다.  
  
### <a name="to-test-the-encryption-wrapper"></a>암호화 래퍼를 테스트 하려면  
  
1.  별도 클래스에는 래퍼를 사용 하는 메서드를 추가 `EncryptData` 메서드는 문자열을 암호화 하 고 사용자에 게 쓰기를 내 문서 폴더입니다.  
  
     [!code-vb[VbVbalrStrings #&78;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  내 문서 폴더 사용자에서 암호화 된 문자열을 읽는 메서드를 추가 하는 래퍼를 사용 하 여 문자열의 암호를 해독 `DecryptData` 메서드.  
  
     [!code-vb[VbVbalrStrings #&79;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  추가 사용자 인터페이스 코드를 호출 하 여 `TestEncoding` 및 `TestDecoding` 메서드.  
  
4.  응용 프로그램을 실행합니다.  
  
     응용 프로그램을 테스트 하는 경우에 해독 되지 않습니다 데이터가 잘못 된 암호를 제공 하는 경우 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.Cryptography></xref:System.Security.Cryptography>   
 <xref:System.Security.Cryptography.DESCryptoServiceProvider></xref:System.Security.Cryptography.DESCryptoServiceProvider>   
 <xref:System.Security.Cryptography.DES></xref:System.Security.Cryptography.DES>   
 <xref:System.Security.Cryptography.TripleDES></xref:System.Security.Cryptography.TripleDES>   
 <xref:System.Security.Cryptography.Rijndael></xref:System.Security.Cryptography.Rijndael>   
 [암호화 서비스](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)
