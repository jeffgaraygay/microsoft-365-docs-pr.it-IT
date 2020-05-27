---
title: Tabella IdentityInfo nello schema di caccia avanzato
description: Informazioni sugli account utente nella tabella IdentityInfo dello schema di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber-caccia alle minacce, Microsoft Threat Protection, Microsoft 365, MTP, M365, ricerca, query, telemetria, riferimento allo schema, kusto, tabella, colonna, tipo di dati, descrizione, AccountInfo, IdentityInfo, account
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 12f8d0995d00daffe8a1ca1c2c8d9dfe25a11581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209776"
---
# <a name="identityinfo"></a><span data-ttu-id="2ce9d-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="2ce9d-104">IdentityInfo</span></span>

<span data-ttu-id="2ce9d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2ce9d-105">**Applies to:**</span></span>
- <span data-ttu-id="2ce9d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2ce9d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2ce9d-107">La `IdentityInfo` tabella nello schema di [ricerca avanzata](advanced-hunting-overview.md) contiene informazioni sugli account utente ottenuti da vari servizi, tra cui Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2ce9d-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="2ce9d-108">Usare questo riferimento per creare query che restituiscono informazioni dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="2ce9d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="2ce9d-109">La tabella è stata rinominata da `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="2ce9d-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="2ce9d-110">Durante la ridenominazione, tutte le query salvate nel portale vengono aggiornate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2ce9d-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="2ce9d-111">Controllare le query salvate altrove.</span><span class="sxs-lookup"><span data-stu-id="2ce9d-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="2ce9d-112">Per informazioni su altre tabelle nello schema per Ricerca avanzata, [vedere il riferimento sulla Ricerca avanzata](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2ce9d-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2ce9d-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="2ce9d-113">Column name</span></span> | <span data-ttu-id="2ce9d-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2ce9d-114">Data type</span></span> | <span data-ttu-id="2ce9d-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ce9d-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="2ce9d-116">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-116">string</span></span> | <span data-ttu-id="2ce9d-117">Identificatore univoco per l'account in Azure AD</span><span class="sxs-lookup"><span data-stu-id="2ce9d-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="2ce9d-118">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-118">string</span></span> | <span data-ttu-id="2ce9d-119">Nome dell'entità utente (UPN) dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="2ce9d-120">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-120">string</span></span> | <span data-ttu-id="2ce9d-121">ID di sicurezza locale (SID) dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="2ce9d-122">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-122">string</span></span> | <span data-ttu-id="2ce9d-123">Identificatore di sicurezza cloud dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="2ce9d-124">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-124">string</span></span> | <span data-ttu-id="2ce9d-125">Nome o nome specificato dell'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="2ce9d-126">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-126">string</span></span> | <span data-ttu-id="2ce9d-127">Cognome, nome della famiglia o cognome dell'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="2ce9d-128">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-128">string</span></span> | <span data-ttu-id="2ce9d-129">Nome dell'account utente visualizzato nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="2ce9d-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="2ce9d-130">In genere una combinazione di un nome o di un cognome, di un'iniziazione centrale e di un ultimo nome.</span><span class="sxs-lookup"><span data-stu-id="2ce9d-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="2ce9d-131">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-131">string</span></span> | <span data-ttu-id="2ce9d-132">Nome del reparto a cui appartiene l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="2ce9d-133">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-133">string</span></span> | <span data-ttu-id="2ce9d-134">Titolo del processo dell'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="2ce9d-135">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-135">string</span></span> | <span data-ttu-id="2ce9d-136">Nome utente dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="2ce9d-137">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-137">string</span></span> | <span data-ttu-id="2ce9d-138">Dominio dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="2ce9d-139">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-139">string</span></span> | <span data-ttu-id="2ce9d-140">Indirizzo SMTP dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="2ce9d-141">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-141">string</span></span> | <span data-ttu-id="2ce9d-142">Indirizzo SIP (Voice of over IP (VOIP) Session Initiation Protocol of the account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-142">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="2ce9d-143">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-143">string</span></span> | <span data-ttu-id="2ce9d-144">Città in cui si trova l'utente dell'account</span><span class="sxs-lookup"><span data-stu-id="2ce9d-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="2ce9d-145">stringa</span><span class="sxs-lookup"><span data-stu-id="2ce9d-145">string</span></span> | <span data-ttu-id="2ce9d-146">Paese/area geografica in cui si trova l'account utente</span><span class="sxs-lookup"><span data-stu-id="2ce9d-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="2ce9d-147">boolean</span><span class="sxs-lookup"><span data-stu-id="2ce9d-147">boolean</span></span> | <span data-ttu-id="2ce9d-148">Indica se l'account è abilitato o meno.</span><span class="sxs-lookup"><span data-stu-id="2ce9d-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="2ce9d-149">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2ce9d-149">Related topics</span></span>
- [<span data-ttu-id="2ce9d-150">Ricerca proattiva delle minacce</span><span class="sxs-lookup"><span data-stu-id="2ce9d-150">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2ce9d-151">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="2ce9d-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2ce9d-152">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="2ce9d-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2ce9d-153">Ricerca delle minacce attraverso dispositivi e posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2ce9d-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2ce9d-154">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="2ce9d-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2ce9d-155">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="2ce9d-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)