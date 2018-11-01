# Ian Horn
## Kentucky Nature Preserves

- I am the project technical lead for Kentucky Nature Preserves Environmental Review tool know as [KY-BAT](https://kynaturepreserves.org "Kentucky Biological Assessment Tool").
- New Maps Plus [Portfolio](https://rihorn.github.io "NMP Portfolio")

### Sample scripts 

 - automation
 
 -- Oracle
 
```
ogr2ogr  -append -overwrite -nlt polygon -nln ksnpc_sites  -a_srs EPSG:3089 -progress -f FileGDB G:/GIS/Data/KY_Singlezone/KSNPC/Biotics5/ogr2ogr.gdb OCI:biotics_dlink/XXXXXXXXXXXXXXXXX:SITE_SHAPE -sql "select SITE_SHAPE.SHAPE shape, CONSERVATION_SITE.CONSERVATION_SITE_ID site_id,  CONSERVATION_SITE.SITE_NAME site_name,  CONSERVATION_SITE.SHAPE_ID shape_id,  CONSERVATION_SITE.SITECODE_BCD sitecode_bcd,  CONSERVATION_SITE.DATA_QC_BY data_qc_by,  CONSERVATION_SITE.SITE_MAPPED_DATE mapped_date, CONSERVATION_SITE.PRIMARY_AREA_ACRES primary_acres, CONSERVATION_SITE.PRIMARY_SECONDARY_AREA_ACRES prim_sec_acres, CONSERVATION_SITE.REC_CREATE_DATE create_date, CONSERVATION_SITE.REC_CREATE_USER create_user, CONSERVATION_SITE.REC_LAST_MOD_DATE mod_date, CONSERVATION_SITE.REC_LAST_MOD_USER mod_user from SITE_SHAPE, CONSERVATION_SITE where SITE_SHAPE.CONSERVATION_SITE_ID = CONSERVATION_SITE.CONSERVATION_SITE_ID"
```
-- SQL Server

```
$ ogr2ogr -overwrite -a_srs EPSG:3089 -f "ESRI Shapefile" "sqlexport.shp" "mssql:server=EEC1VP-SQXX001.EECPPC.ds.ky.gov,1961;database=KNPBase;trusted_connection=yes;" -sql "select * from DBO.COUNTY_BOUNDARIES"
```
