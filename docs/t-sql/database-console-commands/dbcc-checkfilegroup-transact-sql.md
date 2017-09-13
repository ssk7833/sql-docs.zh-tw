---
title: "DBCC CHECKFILEGROUP (TRANSACT-SQL) |Microsoft 文件"
ms.custom:
- SQL2016_New_Updated
ms.date: 07/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CHECKFILEGROUP_TSQL
- DBCC_CHECKFILEGROUP_TSQL
- DBCC CHECKFILEGROUP
- CHECKFILEGROUP
dev_langs:
- TSQL
helpviewer_keywords:
- DBCC CHECKFILEGROUP statement
- database objects [SQL Server], checking
- allocation checks
- integrity [SQL Server], database objects
- filegroups [SQL Server], consistency checks
- table integrity checks [SQL Server]
- checking database objects
ms.assetid: 8c70bf34-7570-4eb6-877a-e35064a1380a
caps.latest.revision: 60
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: c6e5335bd6685e1c547361d931938134becaac84
ms.contentlocale: zh-tw
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-checkfilegroup-transact-sql"></a>DBCC CHECKFILEGROUP (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]檢查配置和結構完整性的所有資料表和索引檢視表中指定的檔案群組的目前資料庫。
![主題連結圖示](../../database-engine/configure-windows/media/topic-link.gif "主題連結圖示") [Transact-SQL 語法慣例](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>語法  
  
```sql
  
DBCC CHECKFILEGROUP   
[  
    [ ( { filegroup_name | filegroup_id | 0 }   
        [ , NOINDEX ]   
  ) ]  
    [ WITH   
        {   
            [ ALL_ERRORMSGS | NO_INFOMSGS ]   
            [ , TABLOCK ]   
            [ , ESTIMATEONLY ]  
            [ , PHYSICAL_ONLY ]    
            [ , MAXDOP  = number_of_processors ]  
        }   
    ]  
]  
```  
  
## <a name="arguments"></a>引數  
 *filegroup_name*  
 這是在目前資料庫中要檢查資料表配置和結構完整性的檔案群組名稱。 若未指定，或指定 0，預設值就是主要檔案群組。 檔案群組名稱必須遵守的規則[識別碼](../../relational-databases/databases/database-identifiers.md)。  
 *filegroup_name*不能是 FILESTREAM 檔案群組。  
  
 *filegroup_id*  
 這是在目前資料庫中要檢查資料表配置和結構完整性的檔案群組識別碼 (ID)。  
  
 NOINDEX  
 指定不應該執行使用者資料表之非叢集索引的大量檢查。 這會減少整體的執行時間。 NOINDEX 不會影響系統資料表，因為 DBCC CHECKFILEGROUP 一律會檢查所有系統資料表索引。  
  
 ALL_ERRORMSGS  
 為每個物件顯示無限數量的錯誤。 系統預設會顯示所有錯誤訊息。 指定或省略這個選項沒有任何作用。  
  
 NO_INFOMSGS  
 隱藏所有參考訊息。  
  
 TABLOCK  
 使 DBCC CHECKFILEGROUP 取得鎖定，而不使用內部資料庫快照集。  
  
 ESTIMATE ONLY  
 顯示利用其他所有指定的選項來執行 DBCC CHECKFILEGROUP 所需要的 tempdb 估計空間量。  
  
 PHYSICAL_ONLY  
 將檢查限制於頁面實體結構、記錄標頭和 B 型樹狀目錄之實體結構的完整性。 專為提供檔案群組實體一致性的小型負擔檢查而設計，這項檢查也能夠偵測到損毀的頁面以及可能危及資料的一般硬體失敗。 完整執行 DBCC CHECKFILEGROUP 所需要的時間可能比舊版多許多。 這個行為的原因如下：  
 -   邏輯檢查更完整。  
 -   部分要檢查的基礎結構更複雜。  
 -   導入了許多新的檢查，以包含新的功能。  
 因此，使用 PHYSICAL_ONLY 選項可能使大型檔案群組 DBCC CHECKFILEGROUP 的執行階段縮短許多，因此，建議您在實際系統上經常使用它。 我們仍建議您定期完整執行 DBCC CHECKFILEGROUP。 這些執行動作的頻率取決於個別商務和實際執行環境特有的因素。 PHYSICAL_ONLY 一律隱含 NO_INFOMSGS，不允許使用任何修復選項。  
  
> [!NOTE]  
>  指定 PHYSICAL_ONLY 會造成 DBCC CHECKFILEGROUP 略過 FILESTREAM 資料的所有檢查。  
  
 MAXDOP  
 **適用於**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2014 SP2 透過[新版](http://go.microsoft.com/fwlink/p/?LinkId=299658)。  
  
 覆寫**的最大平行處理原則程度**組態選項的**sp_configure**陳述式。 MAXDOP 可以超過使用 sp_configure 所設定的值。 如果 MAXDOP 超過使用資源管理員所設定的值，Database Engine 會使用資源管理員 MAXDOP 值，ALTER WORKLOAD GROUP (TRANSACT-SQL) 中所述。 當您使用 MAXDOP 查詢提示時，適用所有搭配 max degree of parallelism 組態選項使用的語意規則。 如需詳細資訊，請參閱 [設定 max degree of parallelism 伺服器組態選項](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)。  
  
> [!CAUTION]  
>  如果 MAXDOP 設定為零，則伺服器會選擇平行處理原則的最大程度。  
  
## <a name="remarks"></a>備註  
DBCC CHECKFILEGROUP 和 DBCC CHECKDB 是類似的 DBCC 命令。 主要差異在於 DBCC CHECKFILEGROUP 只限於單一指定檔案群組和必要的資料表。
DBCC CHECKFILEGROUP 會執行下列命令：
-   [DBCC CHECKALLOC](../../t-sql/database-console-commands/dbcc-checkalloc-transact-sql.md)的檔案群組。  
-   [DBCC CHECKTABLE](../../t-sql/database-console-commands/dbcc-checktable-transact-sql.md)每份資料表和索引檢視表的檔案群組中。  
  
不需要在 DBCC CHECKFILEGROUP 之外，個別執行 DBCC CHECKALLOC 或 DBCC CHECKTABLE。
  
## <a name="internal-database-snapshot"></a>內部資料庫快照集  
DBCC CHECKFILEGROUP 會利用內部資料庫快照集來提供執行這些檢查所需具備的交易一致性。 如需詳細資訊，請參閱[檢視資料庫快照集 &#40; 的疏鬆檔案大小TRANSACT-SQL &#41;](../../relational-databases/databases/view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md)和中的 「 DBCC 內部資料庫快照集使用方式 」 一節[DBCC &#40;TRANSACT-SQL &#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md).
如果無法建立快照集，或指定了 TABLOCK 選項，DBCC CHECKFILEGROUP 會取得鎖定來取得必要的一致性。 在這個情況下，則需要獨佔資料庫鎖定，才能執行配置檢查，而且需要共用資料表鎖定，才能執行資料表檢查。 TABLOCK 會使 DBCC CHECKFILEGROUP 在負荷很重的情況下，仍能在資料庫上執行得比較快，但當 DBCC CHECKFILEGROUP 正在執行時，它會減少資料庫上所能使用的並行。
  
> [!NOTE]  
>  針對 tempdb 執行 DBCC CHECKFILEGROUP 並不會執行任何配置檢查，而且必須取得共用資料表鎖定，才能執行資料表檢查。 這是因為基於效能的考量，tempdb 並無法使用資料庫快照集。 這表示無法取得必要的交易一致性。  
  
## <a name="checking-objects-in-parallel"></a>平行檢查物件  
依預設，DBCC CHECKFILEGROUP 會執行物件的平行檢查。 查詢處理器會自動判斷平行處理原則的程度。 最大平行處理原則程度的設定方式與平行查詢相同。 若要限制 DBCC 檢查可用的處理器數目上限，請使用[sp_configure](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)。 如需詳細資訊，請參閱 [設定 max degree of parallelism 伺服器組態選項](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)。
您可以利用追蹤旗標 2528 來停用平行檢查。 如需詳細資訊，請參閱[追蹤旗標 &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql.md)。
  
## <a name="nonclustered-indexes-on-separate-filegroups"></a>個別檔案群組中的非叢集索引  
如果指定檔案群組中的非叢集索引與另一個檔案群組中的資料表相關聯，就不會檢查索引，因為基底資料表無法用來進行驗證。
如果指定檔案群組中的資料表有另一個檔案群組中的非叢集索引，就不會檢查非叢集索引，原因如下：
-   基底資料表結構不會隨著非叢集索引的結構而不同。 不需要掃描非叢集索引來驗證基底資料表。  
-   DBCC CHECKFILEGROUP 命令只會驗證指定之檔案群組中的物件。  
叢集索引和資料表不能在不同的檔案群組中；因此，先前的考量只適用於非叢集索引。
  
## <a name="partitioned-tables-on-separate-filegroups"></a>個別檔案群組中的資料分割資料表  
當資料分割資料表存在於多個檔案群組中時，DBCC CHECKFILEGROUP 會檢查存在於指定檔案群組中的資料分割資料列集，忽略其他檔案群組中的資料列集。 參考訊息 2594 會指出未檢查的資料分割。 不在指定之檔案群組中的非叢集索引也不會檢查。
  
## <a name="understanding-dbcc-error-messages"></a>了解 DBCC 錯誤訊息  
DBCC CHECKFILEGROUP 命令執行完成之後，[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 錯誤記錄檔中會寫入一則訊息。 如果 DBCC 命令執行成功，該訊息將指出命令已順利完成，並顯示命令執行的時間量。 如果 DBCC 命令由於發生錯誤而在完成檢查之前停止執行，則訊息中會指出命令已經終止，並顯示狀態值以及命令執行的時間量。 下表列出並描述可以包含在訊息中的狀態值。
  
|State|Description|  
|-----------|-----------------|  
|0|已引發錯誤號碼 8930。 這表示中繼資料損毀使 DBCC 命令終止。|  
|1|已引發錯誤號碼 8967。 發生內部 DBCC 錯誤。|  
|2|修復緊急模式資料庫期間發生失敗。|  
|3|這表示中繼資料損毀使 DBCC 命令終止。|  
|4|偵測到判斷提示或存取違規。|  
|5|發生使 DBCC 命令終止的未知錯誤。|  
  
## <a name="error-reporting"></a>錯誤報告  
小型傾印檔案 (SQLDUMP*nnnn*.txt) 中建立[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]每當 DBCC CHECKFILEGROUP 偵測到損毀錯誤時的記錄檔目錄。 當 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的執行個體已啟用「功能使用方式」資料收集及「錯誤報告」功能時，這個檔案會自動轉送到 [!INCLUDE[msCoName](../../includes/msconame-md.md)]。 收集的資料是用來提升 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的功能。
傾印檔案包含 DBCC CHECKFILEGROUP 命令的結果以及其他診斷輸出。 這個檔案具有限制的任意存取控制清單 (DACL)。 存取限於[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]服務帳戶和成員的**sysadmin**角色。 根據預設， **sysadmin**角色包含 Windows BUILTIN\Administrators 群組和本機系統管理員群組的所有成員。 如果資料收集程序失敗，DBCC 命令不會失敗。
  
## <a name="resolving-errors"></a>解決錯誤  
如果 DBCC CHECKFILEGROUP 報告任何錯誤，建議您從資料庫備份中還原資料庫。 請注意，DBCC CHECKFILEGROUP 不能指定修復選項。
如果備份不存在，指定修復選項來執行 DBCC CHECKDB，便可以更正報告的錯誤。 如果報告錯誤，所用的修復選項會指定在清單尾端。 利用 REPAIR_ALLOW_DATA_LOSS 選項來更正錯誤可能需要刪除某些頁面，因而也需要刪除某些資料。
  
## <a name="result-sets"></a>結果集  
DBCC CHECKFILEGROUP 會傳回下列結果集 (值可能不同)：
-   當指定 ESTIMATEONLY 或 NO_INFOMSGS 時除外。  
-   對於目前資料庫 (如果未指定資料庫)，是否指定了任何選項 (除了 NOINDEX 以外)。  
  
```sql
DBCC results for 'master'.  
DBCC results for 'sys.sysrowsetcolumns'.  
There are 630 rows in 7 pages for object 'sys.sysrowsetcolumns'.  
DBCC results for 'sys.sysrowsets'.  
There are 97 rows in 1 pages for object 'sys.sysrowsets'.  
DBCC results for 'sysallocunits'.  
There are 195 rows in 3 pages for object 'sysallocunits'.  
  
There are 2340 rows in 16 pages for object 'spt_values'.  
DBCC results for 'MSreplication_options'.  
There are 2 rows in 1 pages for object 'MSreplication_options'.  
CHECKFILEGROUP found 0 allocation errors and 0 consistency errors in database 'master'.  
DBCC execution completed. If DBCC printed error messages, contact your system administrator.  
```  
  
如果未指定 NO_INFOMSGS，DBCC CHECKFILEGROUP 會傳回：
  
```sql
DBCC execution completed. If DBCC printed error messages, contact your system administrator.  
```  
 如果未指定 ESTIMATEONLY，DBCC CHECKFILEGROUP 會傳回 (值可能不同)：  

```sql
Estimated TEMPDB space needed for CHECKALLOC (KB)
-------------------------------------------------   
15  
  
(1 row(s) affected)  
  
Estimated TEMPDB space needed for CHECKTABLES (KB)   
--------------------------------------------------   
207  
  
(1 row(s) affected)  
  
DBCC execution completed. If DBCC printed error messages, contact your system administrator.  
```  
  
## <a name="permissions"></a>Permissions  
需要 **系統管理員** 固定伺服器角色或 **db_owner** 固定資料庫角色中的成員資格。
  
## <a name="examples"></a>範例  
### <a name="a-checking-the-primary-filegroup-in-the-a-database"></a>A. 檢查資料庫中的 PRIMARY 檔案群組  
以下範例會檢查目前資料庫的主要檔案群組。
  
```sql  
  
DBCC CHECKFILEGROUP;  
GO  
```  
  
### <a name="b-checking-the-adventureworks-primary-filegroup-without-nonclustered-indexes"></a>B. 檢查 AdventureWorks PRIMARY 檔案群組，不含非叢集索引  
下列範例會檢查`AdventureWorks2012`資料庫主要檔案群組 （不包括非叢集索引） 藉由指定主要檔案群組中，識別碼和`NOINDEX`。
  
```sql  
USE AdventureWorks2012;  
GO  
DBCC CHECKFILEGROUP (1, NOINDEX);  
GO  
```  
  
### <a name="c-checking-the-primary-filegroup-with-options"></a>C. 檢查 PRIMARY 檔案群組，含選項  
下列範例會檢查 `master` 資料庫主要檔案群組並指定 `ESTIMATEONLY` 選項。
  
```sql  
USE master;  
GO  
DBCC CHECKFILEGROUP (1)  
WITH ESTIMATEONLY;  
```  
  
## <a name="see-also"></a>另請參閱  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)  
[FILEGROUP_ID &#40;TRANSACT-SQL &#41;](../../t-sql/functions/filegroup-id-transact-sql.md)  
[sp_helpfile &#40;TRANSACT-SQL &#41;](../../relational-databases/system-stored-procedures/sp-helpfile-transact-sql.md)  
[sp_helpfilegroup &#40;TRANSACT-SQL &#41;](../../relational-databases/system-stored-procedures/sp-helpfilegroup-transact-sql.md)  
[sys.sysfilegroups &#40;TRANSACT-SQL &#41;](../../relational-databases/system-compatibility-views/sys-sysfilegroups-transact-sql.md)  
[DBCC CHECKDB &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-checkdb-transact-sql.md)  
[DBCC CHECKALLOC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-checkalloc-transact-sql.md)  
[DBCC CHECKTABLE &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-checktable-transact-sql.md)
  
  
