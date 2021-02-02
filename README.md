# HackerRank_SQL
Answers of some challenged questions in HackerRank
1. Weather Observation Station 20 <br>
Query the median of the Northern Latitudes (LAT_N) from STATION and round your answer to  decimal places.<br>
`Select round(S.LAT_N,4) from station AS S 
where (select count(Lat_N) from station where Lat_N < S.LAT_N ) = (select count(Lat_N) from station where Lat_N > S.LAT_N);`
2. Occupations<br>Pivot the Occupation column in Occupations so that each name is sorted alphabetically and displayed underneath its corresponding occupation. the output column headers should be Doctor, Professor, Singer, and Actor, respectively<br>
`SET @r1=0, @r2=0, @r3 =0, @r4=0;
SELECT MIN(Doctor), MIN(Professor), MIN(Singer), MIN(Actor) FROM
(SELECT CASE Occupation WHEN 'Doctor' THEN @r1:=@r1+1
                       WHEN 'Professor' THEN @r2:=@r2+1
                       WHEN 'Singer' THEN @r3:=@r3+1
                       WHEN 'Actor' THEN @r4:=@r4+1 END
       AS RowLine,
       CASE WHEN Occupation = 'Doctor' THEN Name END AS Doctor,
       CASE WHEN Occupation = 'Professor' THEN Name END AS Professor,
       CASE WHEN Occupation = 'Singer' THEN Name END AS Singer,
       CASE WHEN Occupation = 'Actor' THEN Name END AS Actor
       FROM OCCUPATIONS ORDER BY Name) AS t
GROUP BY RowLine;`
