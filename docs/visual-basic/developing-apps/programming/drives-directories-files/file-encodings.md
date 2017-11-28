---
title: "파일 인코딩(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- character encodings
- files [Visual Basic], encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: deaab4371ab0d5d15c627bfd6352a7090bf08024
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="file-encodings-visual-basic"></a><span data-ttu-id="61464-102">파일 인코딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="61464-102">File Encodings (Visual Basic)</span></span>
<span data-ttu-id="61464-103">문자 인코딩이라고도 하는 파일 인코딩은 텍스트 처리 시 문자를 나타내는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61464-103">File encodings, also known as character encodings, specify how to represent characters when text processing.</span></span> <span data-ttu-id="61464-104">처리할 수 있거나 없는 언어 문자를 기준으로 특정 인코딩이 다른 인코딩보다 선호될 수 있지만, 일반적으로 유니코드가 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="61464-104">One encoding may be preferable over another in terms of which language characters it can or cannot handle, although Unicode is usually preferred.</span></span>  
  
 <span data-ttu-id="61464-105">파일을 읽거나 쓸 때 파일 인코딩을 잘못 일치시키면 예외 또는 잘못된 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61464-105">When reading from or writing to files, improperly matching file encodings may result in exceptions or incorrect results.</span></span>  
  
## <a name="types-of-encodings"></a><span data-ttu-id="61464-106">인코딩 형식</span><span class="sxs-lookup"><span data-stu-id="61464-106">Types of Encodings</span></span>  
 <span data-ttu-id="61464-107">파일 작업 시 기본 설정 인코딩은 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="61464-107">Unicode is the preferred encoding when working with files.</span></span> <span data-ttu-id="61464-108">유니코드는 게시에 사용되는 전문 기호 및 특수 문자를 포함하여 첨단 컴퓨팅에서 사용되는 모든 문자를 16비트 코드 값으로 나타내는 전 세계 문자 인코딩 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="61464-108">Unicode is a worldwide character-encoding standard that uses 16-bit code values to represent all the characters used in modern computing, including technical symbols and special characters used in publishing.</span></span>  
  
 <span data-ttu-id="61464-109">이전 문자 인코딩 표준은 8비트 코드 값 또는 8비트 값의 조합을 사용하여 특정 언어나 지역에서 사용되는 문자를 나타내는 Windows ANSI 문자 집합 등의 기존 문자 집합으로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61464-109">Previous character-encoding standards consisted of traditional character sets, such as the Windows ANSI character set that uses 8-bit code values, or combinations of 8-bit values, to represent the characters used in a specific language or geographical region.</span></span>  
  
## <a name="encoding-class"></a><span data-ttu-id="61464-110">Encoding 클래스</span><span class="sxs-lookup"><span data-stu-id="61464-110">Encoding Class</span></span>  
 <span data-ttu-id="61464-111"><xref:System.Text.Encoding> 클래스는 문자 인코딩을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61464-111">The <xref:System.Text.Encoding> class represents a character encoding.</span></span> <span data-ttu-id="61464-112">이 표에서는 사용 가능한 인코딩 형식을 나열하고 각 인코딩 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61464-112">This table lists the type of encodings available and describes each.</span></span>  
  
|<span data-ttu-id="61464-113">이름</span><span class="sxs-lookup"><span data-stu-id="61464-113">Name</span></span>|<span data-ttu-id="61464-114">설명</span><span class="sxs-lookup"><span data-stu-id="61464-114">Description</span></span>|
|---|---|    
|<xref:System.Text.ASCIIEncoding>|<span data-ttu-id="61464-115">유니코드 문자의 ASCII 문자 인코딩을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61464-115">Represents an ASCII character encoding of Unicode characters.</span></span>|  
|<xref:System.Text.UnicodeEncoding>|<span data-ttu-id="61464-116">유니코드 문자의 UTF-16 인코딩을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61464-116">Represents a UTF-16 encoding of Unicode characters.</span></span>|  
|<xref:System.Text.UTF32Encoding>|<span data-ttu-id="61464-117">유니코드 문자의 UTF-32 인코딩을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61464-117">Represents a UTF-32 encoding of Unicode characters.</span></span>|  
|<xref:System.Text.UTF7Encoding>|<span data-ttu-id="61464-118">유니코드 문자의 UTF-7 인코딩을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61464-118">Represents a UTF-7 encoding of Unicode characters.</span></span>|  
|<xref:System.Text.UTF8Encoding>|<span data-ttu-id="61464-119">유니코드 문자의 UTF-8 인코딩을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61464-119">Represents a UTF-8 encoding of Unicode characters.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61464-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61464-120">See Also</span></span>  
 [<span data-ttu-id="61464-121">파일 읽기</span><span class="sxs-lookup"><span data-stu-id="61464-121">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [<span data-ttu-id="61464-122">파일에 쓰기</span><span class="sxs-lookup"><span data-stu-id="61464-122">Writing to Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
