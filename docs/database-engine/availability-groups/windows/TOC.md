# [概觀](overview-of-always-on-availability-groups-sql-server.md)  
## [互通性](always-on-availability-groups-interoperability-sql-server.md)  
## [技術和功能](always-on-availability-groups-sql-server.md)  

# 快速入門
## [快速入門](getting-started-with-always-on-availability-groups-sql-server.md)  
## [先決條件、限制與建議](prereqs-restrictions-recommendations-always-on-availability.md)  
## [建立及設定](creation-and-configuration-of-availability-groups-sql-server.md)  
### [精靈](use-the-availability-group-wizard-sql-server-management-studio.md)  
### [對話](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
### [Transact-SQL](create-an-availability-group-transact-sql.md)  
### [PowerShell](create-an-availability-group-sql-server-powershell.md)  
### [Azure 虛擬機器](http://docs.microsoft.com/azure/virtual-machines/windows/sql/virtual-machines-windows-portal-sql-availability-group-overview)
## [接聽程式](create-or-configure-an-availability-group-listener-sql-server.md)  

# 概念
## [自動植入次要複本](automatic-seeding-secondary-replicas.md)
## [可用性群組原則](always-on-policies-for-operational-issues-always-on-availability.md)  
## [可用性模式](availability-modes-always-on-availability-groups.md)  
## [在次要複本上備份](active-secondaries-backup-on-secondary-replicas-always-on-availability-groups.md)  
## [基本可用性群組](basic-availability-groups-always-on-availability-groups.md)  
## [用戶端連線](about-client-connection-access-to-availability-replicas-sql-server.md)  
## [用戶端連線能力](always-on-client-connectivity-sql-server.md)  
## [分散式可用性群組](distributed-availability-groups.md)  
## [網域獨立的可用性群組](domain-independent-availability-groups.md)  
## [增強型資料庫容錯移轉](enhanced-database-failover.md)
### [資料庫健全狀況偵測](sql-server-always-on-database-health-detection-failover-option.md)  
## [容錯移轉叢集與可用性群組](failover-clustering-and-always-on-availability-groups-sql-server.md)  
## [容錯移轉與容錯移轉模式](failover-and-failover-modes-always-on-availability-groups.md)  
## [自動容錯移轉的彈性容錯移轉原則](flexible-automatic-failover-policy-availability-group.md)  
## 與其他功能的互通性
### [變更追蹤與變更資料擷取](replicate-track-change-data-capture-always-on-availability.md)  
### [設定複寫](configure-replication-for-always-on-availability-groups-sql-server.md)  
### [自主資料庫](contained-databases-with-always-on-availability-groups-sql-server.md)  
### [資料庫快照集](database-snapshots-with-always-on-availability-groups-sql-server.md)  
### [分散式交易](transactions-always-on-availability-and-database-mirroring.md)  
#### [叢集 DTC](cluster-dtc-for-sql-server-2016-availability-groups.md)  
### [加密的資料庫](encrypted-databases-with-always-on-availability-groups-sql-server.md)  
### [容錯移轉叢集執行個體](analysis-services-with-always-on-availability-groups.md)  
### [FILESTREAM 與 FileTable](filestream-and-filetable-with-always-on-availability-groups-sql-server.md)  
### [從記錄傳送移轉](prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
### [遠端 Blob 存放區 (RBS)](remote-blob-store-rbs-and-always-on-availability-groups-sql-server.md)  
#### [發行集資料庫](maintaining-an-always-on-publication-database-sql-server.md)  
#### [訂閱者](replication-subscribers-and-always-on-availability-groups-sql-server.md)  
### [Reporting Services](reporting-services-with-always-on-availability-groups-sql-server.md)  
### [Service Broker](service-broker-with-always-on-availability-groups-sql-server.md)  
## [接聽程式、用戶端與容錯移轉](listeners-client-connectivity-application-failover.md)  
## [登入與作業](logins-and-jobs-for-availability-group-databases.md)  
## [工作階段期間複本之間可能發生的失敗](possible-failures-during-sessions-between-availability-replicas-sql-server.md)  
## [僅讀取級別](read-scale-availability-groups.md)  
## [可讀取的次要複本](active-secondaries-readable-secondary-replicas-always-on-availability-groups.md)  

# [使用說明指南](administration-of-an-availability-group-sql-server.md)  
## 設定可用性群組 
### [變更複本可用性](change-the-availability-mode-of-an-availability-replica-sql-server.md)  
### [變更複本容錯移轉模式](change-the-failover-mode-of-an-availability-replica-sql-server.md)  
### [設定自動植入](automatically-initialize-always-on-availability-group.md)  
### [設定複本的備份](configure-backup-on-availability-replicas-sql-server.md)  
### [設定彈性容錯移轉原則](configure-flexible-automatic-failover-policy.md)  
### [設定複本的備份](configure-backup-on-availability-replicas-sql-server.md)  
### [設定分散式可用性群組](configure-distributed-availability-groups.md)
### [設定分散式交易](configure-availability-group-for-distributed-transactions.md)
### [設定唯讀存取複本](configure-read-only-access-on-an-availability-replica-sql-server.md)  
### [設定唯讀路由](configure-read-only-routing-for-an-availability-group-sql-server.md)  
### [移除接聽程式](remove-an-availability-group-listener-sql-server.md)  
### [加入次要資料庫](join-a-secondary-database-to-an-availability-group-sql-server.md)  
### [開始進行資料移動](start-data-movement-on-an-always-on-secondary-database-sql-server.md)  
### [手動準備次要資料庫](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
### [在新增或修改複本時指定端點 URL](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
### [加入次要複本](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
### [調整壓縮](tune-compression-for-availability-group.md)  
### [為組態進行疑難排解](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
## [設定執行個體](configuration-of-a-server-instance-for-always-on-availability-groups-sql-server.md)  
### [啟用與停用](enable-and-disable-always-on-availability-groups-sql-server.md)  
### [建立資料庫鏡像端點 (PowerShell)](database-mirroring-always-on-availability-groups-powershell.md)  
### [建立叢集 DTC](create-clustered-dtc-for-an-always-on-availability-group.md)  
## [監視](monitoring-of-availability-groups-sql-server.md)  
### [Transact-SQL](monitor-availability-groups-transact-sql.md)  
### [SQL Server Management Studio](use-object-explorer-details-to-monitor-availability-groups.md)  
### [檢視可用性群組屬性](view-availability-group-properties-sql-server.md)  
### [檢視複本屬性](view-availability-replica-properties-sql-server.md)  
### [檢視接聽程式屬性](view-availability-group-listener-properties-sql-server.md)  
## 作業
### 新增資料庫
#### [對話](availability-group-add-a-database.md)  
#### [精靈](availability-group-add-database-to-group-wizard.md)  
### [新增複本 - 精靈](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
### [新增次要複本](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
### [變更工作階段逾時期間](change-the-session-timeout-period-for-an-availability-replica-sql-server.md)  
### [變更 HADR 叢集內容](change-the-hadr-cluster-context-of-server-instance-sql-server.md)  
### [容錯移轉 - 精靈](use-the-fail-over-availability-group-wizard-sql-server-management-studio.md)  
### [強制手動容錯移轉](perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
### [規劃的手動容錯移轉](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md)  
### [移除可用性群組](remove-an-availability-group-sql-server.md)  
### [移除主要資料庫](remove-a-primary-database-from-an-availability-group-sql-server.md)  
### [移除複本](remove-a-secondary-replica-from-an-availability-group-sql-server.md)  
### [移除次要資料庫](remove-a-secondary-database-from-an-availability-group-sql-server.md)  
### [繼續可用性資料庫](resume-an-availability-database-sql-server.md)  
### [暫止可用性資料庫](suspend-an-availability-database-sql-server.md)  
### [讓可用性群組離線](take-an-availability-group-offline-sql-server.md)  
### [為失敗的新增檔案作業進行疑難排解](troubleshoot-a-failed-add-file-operation-always-on-availability-groups.md)  
### [升級複本執行個體](upgrading-always-on-availability-group-replica-instances.md)  
### [以原則檢視健康情況](use-always-on-policies-to-view-the-health-of-an-availability-group-sql-server.md)  


# 參考
## [PowerShell Cmdlet](overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
## [Transact-SQL](transact-sql-statements-for-always-on-availability-groups.md)  

# 資源
## 對話方塊和精靈
### [新增 IP 位址對話方塊](add-ip-address-dialog-box-sql-server-management-studio.md)  
### [設定可用性群組的唯讀路由](configure-read-only-routing-for-an-availability-group-sql-server.md)  
### [移除可用性群組接聽程式](remove-an-availability-group-listener-sql-server.md)  
### [指定可用性群組選項頁面 (新增可用性群組精靈/新增資料庫精靈)](specify-availability-group-name-page.md)  
### [選取資料庫頁面 (新增可用性群組精靈和新增資料庫精靈)](select-databases-page-new-availability-group-wizard-and-add-database-wizard.md)  
### [指定複本頁面 (新增可用性群組精靈：新增複本精靈)](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md)  
### [輸入密碼頁面 (新增複本精靈)](enter-passwords-page-add-replica-wizard.md)  
### [選取初始資料同步處理頁面 (AlwaysOn 可用性群組精靈)](select-initial-data-synchronization-page-always-on-availability-group-wizards.md)  
### [驗證頁面 (AlwaysOn 可用性群組精靈)](validation-page-always-on-availability-group-wizards.md)  
### [摘要頁面 (AlwaysOn 可用性群組精靈)](summary-page-always-on-availability-group-wizards.md)  
### [進度頁面 (AlwaysOn 可用性群組精靈)](progress-page-always-on-availability-group-wizards.md)  
### [結果頁面 (Always On 可用性群組精靈)](results-page-always-on-availability-group-wizards.md)  
### [可用性群組 - 與現有的次要複本頁面連線](connect-to-existing-secondary-replicas-page.md)  
## [使用 AlwaysOn 儀表板 (SQL Server Management Studio)](use-the-always-on-dashboard-sql-server-management-studio.md)  
### [選項 (SQL Server AlwaysOn、儀表板頁面)](options-sql-server-always-on-dashboard-page.md)  
### [原則評估結果 (AlwaysOn)](policy-evaluation-result-always-on.md)  
### [可用性複本屬性 (一般頁面)](availability-replica-properties-general-page.md)  
### [可用性群組屬性：新增可用性群組 (一般頁面)](availability-group-properties-new-availability-group-general-page.md) 
### [可用性群組屬性：新增可用性群組 (備份喜好設定頁面)](availability-group-properties-new-availability-group-backup-preferences-page.md)  
## 原則
### [可用性資料庫已暫止](availability-database-is-suspended.md)  
### [可用性群組已離線](availability-group-is-offline.md)  
### [可用性群組尚未準備進行自動容錯移轉](availability-group-is-not-ready-for-automatic-failover.md)  
### [可用性複本沒有健康情況良好的角色](availability-replica-does-not-have-a-healthy-role.md)  
### [可用性複本已中斷連線](availability-replica-is-disconnected.md)  
### [可用性複本未聯結](availability-replica-is-not-joined.md)  
### [可用性資料庫的資料同步狀態健康情況不佳](data-synchronization-state-of-availability-database-is-not-healthy.md)  
### [某些可用性資料庫的資料同步狀態健康情況不佳](data-synchronization-state-of-some-availability-database-is-not-healthy.md)  
### [次要資料庫未聯結](secondary-database-is-not-joined.md)  
### [某些可用性複本已中斷連線](some-availability-replicas-are-disconnected.md)  
### [某些可用性複本未同步資料](some-availability-replicas-are-not-synchronizing-data.md)  
### [某些可用性複本沒有健康情況良好的角色](some-availability-replicas-do-not-have-a-healthy-role.md)  
### [某些同步複本並未同步處理](some-synchronous-replicas-are-not-synchronized.md)  
### [WSFC 叢集服務已離線](wsfc-cluster-service-is-offline.md)  
