# HackerRank_SQL
Answers of some challenged questions in HackerRank
1. Weather Observation Station 20 <br>
Query the median of the Northern Latitudes (LAT_N) from STATION and round your answer to  decimal places.<br>
`Select round(S.LAT_N,4) from station AS S 
where (select count(Lat_N) from station where Lat_N < S.LAT_N ) = (select count(Lat_N) from station where Lat_N > S.LAT_N);`
