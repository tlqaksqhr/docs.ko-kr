---
title: "메타데이터 시스템 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d0c729850e25e9fe4bec37dc366053de8c56f210
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="48f38-102">메타데이터 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="48f38-102">Extending the Metadata System</span></span>
<span data-ttu-id="48f38-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 메타데이터 시스템은 서비스 기반 응용 프로그램 구현에 필요한 메타데이터를 나타내는 클래스 및 인터페이스 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="48f38-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="48f38-104">클래스를 수정 또는 확장하거나 인터페이스를 구현 및 구성하여 WSDL(웹 서비스 기술 언어) 확장이나 사용자 지정 WS-PolicyAttachments 어설션 같은 사용자 지정 메타데이터를 내보내고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="48f38-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="48f38-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="48f38-105">In This Section</span></span>  
 [<span data-ttu-id="48f38-106">WCF 확장에 대 한 사용자 지정 메타 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="48f38-106">Exporting Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="48f38-107"><xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> 인터페이스를 구현 및 사용하여 사용자 지정 정책 어설션을 WSDL 문서에 포함하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="48f38-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="48f38-108">WCF 확장에 대 한 사용자 지정 메타 데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="48f38-108">Importing Custom Metadata for a WCF Extension</span></span>](../../../../docs/framework/wcf/extending/importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="48f38-109"><xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 인터페이스를 구현 및 사용하여 WSDL 문서의 사용자 지정 정책 어설션을 읽고 응답하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="48f38-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="48f38-110">게시 하 고 사용자 지정 바인딩을 통해 메타 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="48f38-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="48f38-111">사용자 지정 바인딩을 통해 메타데이터를 교환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="48f38-111">Describes how to exchange metadata over custom bindings.</span></span>
