---
title: "버전 2.0에서 System.Uri 네임스페이스 변경 내용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 버전 2.0에서 System.Uri 네임스페이스 변경 내용
몇 가지 변경 된는 <xref:System.Uri?displayProperty=fullName> 클래스입니다.  이러한 변경 내용을 잘못 된 동작이 수정 유용성을 강화 하 고 보안 강화.  
  
## 오래 되어 사용 되지 않는 멤버  
 생성자:  
  
-   모든 생성자는 `dontEscape` 매개 변수.  
  
 방법:  
  
-   <xref:System.Uri.CheckSecurity%2A>  
  
-   <xref:System.Uri.Escape%2A>  
  
-   <xref:System.Uri.Canonicalize%2A>  
  
-   <xref:System.Uri.Parse%2A>  
  
-   <xref:System.Uri.IsReservedCharacter%2A>  
  
-   <xref:System.Uri.IsBadFileSystemCharacter%2A>  
  
-   <xref:System.Uri.IsExcludedCharacter%2A>  
  
-   <xref:System.Uri.EscapeString%2A>  
  
## 변경 내용  
  
-   쿼리 부분 \(파일, ftp 및 기타\)이 없는 것으로 알려진 URI 체계를 '?' 문자는 항상 이스케이프 및 부분으로 간주 되지 않습니다는 <xref:System.Uri.Query%2A> 파트.  
  
-   전체 이스케이프 해제 하면 요청 되지 않는 경우 암시적 파일 Uri \(폼 "c:\\directory\\file@name.txt"\)의 조각 문자 \('\#'\)를 항상 이스케이프 됩니다 또는 <xref:System.Uri.LocalPath%2A> 는 `true`.  
  
-   UNC 호스트 이름 지원 제거 되었습니다. 국제 호스트 이름을 나타내는 IDN 사양이 채택 되었습니다.  
  
-   <xref:System.Uri.LocalPath%2A>항상 완전히 이스케이프 해제 된 문자열을 반환합니다.  
  
-   <xref:System.Uri.ToString%2A>이스케이프 된 '%'를 이스케이프 해제 되지 않습니다 '?', '\#' 문자.  
  
-   <xref:System.Uri.Equals%2A>이제 포함의 <xref:System.Uri.Query%2A> 여부 검사에서 부.  
  
-   연산자 "\= \="및"\! \=" 재정의 하 고 연결 하는 <xref:System.Uri.Equals%2A> 메서드.  
  
-   <xref:System.Uri.IsLoopback%2A>이제 일관성 있는 결과 생성합니다.  
  
-   URI "`file:///path`" 더 이상 "file:\/\/path"로 변환 됩니다.  
  
-   "\#"은 이제는 호스트 이름 종결자로 인식 됩니다.  즉, "http:\/\/consoto.com\#fragment"는 이제 "http:\/\/contoso.com\/\#fragment"으로 변환 됩니다.  
  
-   기본 URI와 단편 결합 하면 버그가 수정 되었습니다.  
  
-   버그에서 <xref:System.Uri.HostNameType%2A> 고정 됩니다.  
  
-   NNTP 구문 분석 버그 해결 되었습니다.  
  
-   HTTP:contoso.com 폼의 URI는 이제는 구문 분석 예외가 throw 됩니다.  
  
-   프레임 워크는 URI의 사용자 정보를 올바르게 처리합니다.  
  
-   URI 경로 압축 끊어진된 URI 루트 위의 파일 시스템을 통과할 수 없습니다 수정 됩니다.  
  
## 참고 항목  
 <xref:System.Uri?displayProperty=fullName>