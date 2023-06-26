CREATE EXTERNAL TABLE `stediproject_database2`.`accelerometer_landing`(
  `timestamp` bigint COMMENT 'from deserializer',
  `user` string COMMENT 'from deserializer',
  `x` double COMMENT 'from deserializer',
  `y` double COMMENT 'from deserializer',
  `z` double COMMENT 'from deserializer')
ROW FORMAT SERDE
  'org.openx.data.jsonserde.JsonSerDe'
WITH SERDEPROPERTIES (
  'paths'='timeStamp,user,x,y,z')
STORED AS INPUTFORMAT
  'org.apache.hadoop.mapred.TextInputFormat'
OUTPUTFORMAT
  'org.apache.hadoop.hive.ql.io.HiveIgnoreKeyTextOutputFormat'
LOCATION
  's3://stediproject-accelerometerlanding/'
TBLPROPERTIES (
  'classification'='json')


<img width="788" alt="accelerometer_landing_screenshot" src="https://github.com/elyseelc/stedi_project_udacity/assets/128007448/6b16bbab-66ff-485d-99bc-75b2579cb54f">
