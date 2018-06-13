---
title: '방법: 설치된 WPF 버전 확인'
ms.date: 03/30/2017
helpviewer_keywords:
- version [WPF], finding
ms.assetid: 99971cef-e218-4f9f-a4c1-350332741860
ms.openlocfilehash: c59fa0d0a4d94c6e6a2ab72a4cd7a3c066649fb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545853"
---
# <a name="how-to-determine-the-installed-version-of-wpf"></a><span data-ttu-id="53c9d-102">방법: 설치된 WPF 버전 확인</span><span class="sxs-lookup"><span data-stu-id="53c9d-102">How to: Determine the Installed Version of WPF</span></span>
<span data-ttu-id="53c9d-103">현재 설치 된 버전에 대 한 버전 번호 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 에 위치한는 **레지스트리**합니다.</span><span class="sxs-lookup"><span data-stu-id="53c9d-103">The version number for the current installed version of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is located in the **Registry**.</span></span>  
  
 <span data-ttu-id="53c9d-104">버전 번호를 찾으려면:</span><span class="sxs-lookup"><span data-stu-id="53c9d-104">To find the version number:</span></span>  
  
1.  <span data-ttu-id="53c9d-105">**시작** 메뉴에서 **실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="53c9d-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="53c9d-106">**열려**, 형식 **regedit.exe**합니다.</span><span class="sxs-lookup"><span data-stu-id="53c9d-106">In **Open**, type **regedit.exe**.</span></span>  
  
3.  <span data-ttu-id="53c9d-107">다음 키를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="53c9d-107">Open the following key:</span></span>  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.0\Setup\Windows Presentation Foundation`  
  
 <span data-ttu-id="53c9d-108">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 버전 번호에 저장 되는 **버전** 값입니다.</span><span class="sxs-lookup"><span data-stu-id="53c9d-108">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] version number is stored in the **Version** value.</span></span>
