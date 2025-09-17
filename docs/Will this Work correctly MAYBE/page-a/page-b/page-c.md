---
title: Connecting the AWS Adapter Using CloudFormation/Organizations
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
```xml Player Profile Sample (xml)
<player xmlns="http://feed.elasticstats.com/schema/basketball/profile-v7.0.xsd" id="0a98e1b1-81f5-4192-abcb-e41470818a29" status="ACT" full_name="Azzi Fudd" first_name="Azzi" last_name="Fudd" abbr_name="A.Fudd" height="71" position="G" primary_position="NA" jersey_number="35" experience="GR" birth_place="Arlington, VA, USA" updated="2024-10-31T20:04:47Z">
  <league id="affab7b6-647e-4304-bbe2-1f9d68cd0cea" name="NCAA WOMEN" alias="NCAAW"/>
  <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN"/>
  <seasons>
    <season id="a263b759-0702-45fb-803a-b1c0651da16f" year="2024" type="REG">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="34" games_started="30" minutes="899.0" field_goals_made="175" field_goals_att="369" field_goals_pct="0.474" two_points_made="96" two_points_att="188" two_points_pct="0.511" three_points_made="79" three_points_att="181" three_points_pct="0.436" blocked_att="11" free_throws_made="33" free_throws_att="36" free_throws_pct="0.917" offensive_rebounds="22" defensive_rebounds="46" rebounds="68" assists="61" turnovers="35" assists_turnover_ratio="1.74" steals="46" blocks="10" personal_fouls="36" tech_fouls="0" points="462" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="384.84" true_shooting_pct="0.6" efficiency="415" field_goals_at_rim_made="28" field_goals_at_rim_att="40" field_goals_at_rim_pct="0.7" field_goals_at_midrange_made="27" field_goals_at_midrange_att="67" field_goals_at_midrange_pct="0.403" usage_pct="23.85"/>
          <average minutes="26.4" points="13.6" off_rebounds="0.65" def_rebounds="1.35" rebounds="2.0" assists="1.8" steals="1.35" blocks="0.29" turnovers="1.03" personal_fouls="1.06" flagrant_fouls="0.0" blocked_att="0.32" field_goals_made="5.15" field_goals_att="10.85" three_points_made="2.32" three_points_att="5.32" free_throws_made="0.97" free_throws_att="1.06" two_points_made="2.82" two_points_att="5.53" efficiency="12.21" true_shooting_att="11.32"/>
        </statistics>
      </team>
    </season>
    <season id="3880629e-092d-42d4-a84a-a7c226754fa2" year="2024" type="PST">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="6" games_started="6" minutes="189.0" field_goals_made="39" field_goals_att="81" field_goals_pct="0.481" two_points_made="23" two_points_att="45" two_points_pct="0.511" three_points_made="16" three_points_att="36" three_points_pct="0.444" blocked_att="0" free_throws_made="11" free_throws_att="12" free_throws_pct="0.917" offensive_rebounds="3" defensive_rebounds="6" rebounds="9" assists="15" turnovers="9" assists_turnover_ratio="1.67" steals="18" blocks="2" personal_fouls="10" tech_fouls="0" points="105" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="86.28" true_shooting_pct="0.608" efficiency="97" field_goals_at_rim_made="9" field_goals_at_rim_att="15" field_goals_at_rim_pct="0.6" field_goals_at_midrange_made="4" field_goals_at_midrange_att="17" field_goals_at_midrange_pct="0.235" usage_pct="25.12"/>
          <average minutes="31.5" points="17.5" off_rebounds="0.5" def_rebounds="1.0" rebounds="1.5" assists="2.5" steals="3.0" blocks="0.33" turnovers="1.5" personal_fouls="1.67" flagrant_fouls="0.0" blocked_att="0.0" field_goals_made="6.5" field_goals_att="13.5" three_points_made="2.67" three_points_att="6.0" free_throws_made="1.83" free_throws_att="2.0" two_points_made="3.83" two_points_att="7.5" efficiency="16.17" true_shooting_att="14.38"/>
        </statistics>
      </team>
    </season>
    <season id="32896a5b-088f-4814-a45c-fc0f0cf69c04" year="2024" type="CT">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="3" games_started="3" minutes="101.0" field_goals_made="13" field_goals_att="30" field_goals_pct="0.433" two_points_made="7" two_points_att="11" two_points_pct="0.636" three_points_made="6" three_points_att="19" three_points_pct="0.316" blocked_att="1" free_throws_made="6" free_throws_att="6" free_throws_pct="1.0" offensive_rebounds="3" defensive_rebounds="3" rebounds="6" assists="3" turnovers="3" assists_turnover_ratio="1.0" steals="4" blocks="0" personal_fouls="3" tech_fouls="0" points="38" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="32.64" true_shooting_pct="0.582" efficiency="31" field_goals_at_rim_made="0" field_goals_at_rim_att="1" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="3" field_goals_at_midrange_att="3" field_goals_at_midrange_pct="1.0" usage_pct="18.85"/>
          <average minutes="33.7" points="12.7" off_rebounds="1.0" def_rebounds="1.0" rebounds="2.0" assists="1.0" steals="1.33" blocks="0.0" turnovers="1.0" personal_fouls="1.0" flagrant_fouls="0.0" blocked_att="0.33" field_goals_made="4.33" field_goals_att="10.0" three_points_made="2.0" three_points_att="6.33" free_throws_made="2.0" free_throws_att="2.0" two_points_made="2.33" two_points_att="3.67" efficiency="10.33" true_shooting_att="10.88"/>
        </statistics>
      </team>
    </season>
    <season id="cf5dcb91-e9ec-4993-ba42-5d632306b4c8" year="2023" type="REG">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="2" games_started="2" minutes="61.0" field_goals_made="8" field_goals_att="25" field_goals_pct="0.32" two_points_made="4" two_points_att="11" two_points_pct="0.364" three_points_made="4" three_points_att="14" three_points_pct="0.286" blocked_att="1" free_throws_made="2" free_throws_att="2" free_throws_pct="1.0" offensive_rebounds="2" defensive_rebounds="3" rebounds="5" assists="5" turnovers="3" assists_turnover_ratio="1.67" steals="2" blocks="0" personal_fouls="5" tech_fouls="0" points="22" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="25.88" true_shooting_pct="0.425" efficiency="14" field_goals_at_rim_made="0" field_goals_at_rim_att="2" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="2" field_goals_at_midrange_att="4" field_goals_at_midrange_pct="0.5" usage_pct="23.41"/>
          <average minutes="30.5" points="11.0" off_rebounds="1.0" def_rebounds="1.5" rebounds="2.5" assists="2.5" steals="1.0" blocks="0.0" turnovers="1.5" personal_fouls="2.5" flagrant_fouls="0.0" blocked_att="0.5" field_goals_made="4.0" field_goals_att="12.5" three_points_made="2.0" three_points_att="7.0" free_throws_made="1.0" free_throws_att="1.0" two_points_made="2.0" two_points_att="5.5" efficiency="7.0" true_shooting_att="12.94"/>
        </statistics>
      </team>
    </season>
    <season id="a871223e-1e70-419e-8697-c0c1c010a7a9" year="2023" type="PST">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="0" games_started="0" minutes="0.0" field_goals_made="0" field_goals_att="0" field_goals_pct="0.0" two_points_made="0" two_points_att="0" two_points_pct="0.0" three_points_made="0" three_points_att="0" three_points_pct="0.0" blocked_att="0" free_throws_made="0" free_throws_att="0" free_throws_pct="0.0" offensive_rebounds="0" defensive_rebounds="0" rebounds="0" assists="0" turnovers="0" assists_turnover_ratio="0.0" steals="0" blocks="0" personal_fouls="0" tech_fouls="0" points="0" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="0.0" true_shooting_pct="0" efficiency="0" field_goals_at_rim_made="0" field_goals_at_rim_att="0" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="0" field_goals_at_midrange_att="0" field_goals_at_midrange_pct="0.0" usage_pct="0"/>
          <average minutes="0.0" points="0.0" off_rebounds="0.0" def_rebounds="0.0" rebounds="0.0" assists="0.0" steals="0.0" blocks="0.0" turnovers="0.0" personal_fouls="0.0" flagrant_fouls="0.0" blocked_att="0.0" field_goals_made="0.0" field_goals_att="0.0" three_points_made="0.0" three_points_att="0.0" free_throws_made="0.0" free_throws_att="0.0" two_points_made="0.0" two_points_att="0.0" efficiency="0.0" true_shooting_att="0.0"/>
        </statistics>
      </team>
    </season>
    <season id="6d242a1f-93d0-48e4-96c0-45ff92ba607e" year="2023" type="CT">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="0" games_started="0" minutes="0.0" field_goals_made="0" field_goals_att="0" field_goals_pct="0.0" two_points_made="0" two_points_att="0" two_points_pct="0.0" three_points_made="0" three_points_att="0" three_points_pct="0.0" blocked_att="0" free_throws_made="0" free_throws_att="0" free_throws_pct="0.0" offensive_rebounds="0" defensive_rebounds="0" rebounds="0" assists="0" turnovers="0" assists_turnover_ratio="0.0" steals="0" blocks="0" personal_fouls="0" tech_fouls="0" points="0" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="0.0" true_shooting_pct="0" efficiency="0" field_goals_at_rim_made="0" field_goals_at_rim_att="0" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="0" field_goals_at_midrange_att="0" field_goals_at_midrange_pct="0.0" usage_pct="0"/>
          <average minutes="0.0" points="0.0" off_rebounds="0.0" def_rebounds="0.0" rebounds="0.0" assists="0.0" steals="0.0" blocks="0.0" turnovers="0.0" personal_fouls="0.0" flagrant_fouls="0.0" blocked_att="0.0" field_goals_made="0.0" field_goals_att="0.0" three_points_made="0.0" three_points_att="0.0" free_throws_made="0.0" free_throws_att="0.0" two_points_made="0.0" two_points_att="0.0" efficiency="0.0" true_shooting_att="0.0"/>
        </statistics>
      </team>
    </season>
    <season id="99709e03-9678-4ded-b848-3406ff731687" year="2022" type="REG">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="15" games_started="10" minutes="422.0" field_goals_made="89" field_goals_att="195" field_goals_pct="0.456" two_points_made="55" two_points_att="95" two_points_pct="0.579" three_points_made="34" three_points_att="100" three_points_pct="0.34" blocked_att="4" free_throws_made="15" free_throws_att="17" free_throws_pct="0.882" offensive_rebounds="6" defensive_rebounds="23" rebounds="29" assists="29" turnovers="26" assists_turnover_ratio="1.12" steals="20" blocks="5" personal_fouls="15" tech_fouls="0" points="227" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="202.48" true_shooting_pct="0.561" efficiency="176" field_goals_at_rim_made="0" field_goals_at_rim_att="0" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="0" field_goals_at_midrange_att="0" field_goals_at_midrange_pct="0.0" usage_pct="26.65"/>
          <average minutes="28.1" points="15.1" off_rebounds="0.4" def_rebounds="1.53" rebounds="1.93" assists="1.9" steals="1.33" blocks="0.33" turnovers="1.73" personal_fouls="1.0" flagrant_fouls="0.0" blocked_att="0.27" field_goals_made="5.93" field_goals_att="13.0" three_points_made="2.27" three_points_att="6.67" free_throws_made="1.0" free_throws_att="1.13" two_points_made="3.67" two_points_att="6.33" efficiency="11.73" true_shooting_att="13.5"/>
        </statistics>
      </team>
    </season>
    <season id="53f19b98-5b7f-413d-810f-58ddfcbf9a0f" year="2022" type="PST">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="3" games_started="3" minutes="103.0" field_goals_made="17" field_goals_att="49" field_goals_pct="0.347" two_points_made="11" two_points_att="20" two_points_pct="0.55" three_points_made="6" three_points_att="29" three_points_pct="0.207" blocked_att="1" free_throws_made="1" free_throws_att="2" free_throws_pct="0.5" offensive_rebounds="2" defensive_rebounds="8" rebounds="10" assists="4" turnovers="8" assists_turnover_ratio="0.5" steals="6" blocks="2" personal_fouls="2" tech_fouls="0" points="41" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="49.88" true_shooting_pct="0.411" efficiency="22" field_goals_at_rim_made="0" field_goals_at_rim_att="0" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="0" field_goals_at_midrange_att="0" field_goals_at_midrange_pct="0.0" usage_pct="27.56"/>
          <average minutes="34.3" points="13.7" off_rebounds="0.67" def_rebounds="2.67" rebounds="3.33" assists="1.3" steals="2.0" blocks="0.67" turnovers="2.67" personal_fouls="0.67" flagrant_fouls="0.0" blocked_att="0.33" field_goals_made="5.67" field_goals_att="16.33" three_points_made="2.0" three_points_att="9.67" free_throws_made="0.33" free_throws_att="0.67" two_points_made="3.67" two_points_att="6.67" efficiency="7.33" true_shooting_att="16.63"/>
        </statistics>
      </team>
    </season>
    <season id="793b14e0-4575-40d5-a2cf-8c7bdc40de04" year="2022" type="CT">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="3" games_started="0" minutes="69.0" field_goals_made="9" field_goals_att="28" field_goals_pct="0.321" two_points_made="4" two_points_att="10" two_points_pct="0.4" three_points_made="5" three_points_att="18" three_points_pct="0.278" blocked_att="0" free_throws_made="2" free_throws_att="2" free_throws_pct="1.0" offensive_rebounds="1" defensive_rebounds="3" rebounds="4" assists="5" turnovers="4" assists_turnover_ratio="1.25" steals="3" blocks="0" personal_fouls="3" tech_fouls="0" points="25" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="28.88" true_shooting_pct="0.433" efficiency="14" field_goals_at_rim_made="0" field_goals_at_rim_att="0" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="0" field_goals_at_midrange_att="0" field_goals_at_midrange_pct="0.0" usage_pct="23.15"/>
          <average minutes="23.0" points="8.3" off_rebounds="0.33" def_rebounds="1.0" rebounds="1.33" assists="1.7" steals="1.0" blocks="0.0" turnovers="1.33" personal_fouls="1.0" flagrant_fouls="0.0" blocked_att="0.0" field_goals_made="3.0" field_goals_att="9.33" three_points_made="1.67" three_points_att="6.0" free_throws_made="0.67" free_throws_att="0.67" two_points_made="1.33" two_points_att="3.33" efficiency="4.67" true_shooting_att="9.63"/>
        </statistics>
      </team>
    </season>
    <season id="627a6180-4607-4323-91c9-193d5f0808ce" year="2021" type="REG">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="6" games_started="6" minutes="184.0" field_goals_made="20" field_goals_att="55" field_goals_pct="0.364" two_points_made="7" two_points_att="23" two_points_pct="0.304" three_points_made="13" three_points_att="32" three_points_pct="0.406" blocked_att="3" free_throws_made="15" free_throws_att="16" free_throws_pct="0.938" offensive_rebounds="2" defensive_rebounds="13" rebounds="15" assists="2" turnovers="9" assists_turnover_ratio="0.22" steals="6" blocks="4" personal_fouls="9" tech_fouls="0" points="68" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="62.04" true_shooting_pct="0.548" efficiency="50" field_goals_at_rim_made="0" field_goals_at_rim_att="0" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="0" field_goals_at_midrange_att="0" field_goals_at_midrange_pct="0.0" usage_pct="19.78"/>
          <average minutes="30.7" points="11.3" off_rebounds="0.33" def_rebounds="2.17" rebounds="2.5" assists="0.3" steals="1.0" blocks="0.67" turnovers="1.5" personal_fouls="1.5" flagrant_fouls="0.0" blocked_att="0.5" field_goals_made="3.33" field_goals_att="9.17" three_points_made="2.17" three_points_att="5.33" free_throws_made="2.5" free_throws_att="2.67" two_points_made="1.17" two_points_att="3.83" efficiency="8.33" true_shooting_att="10.34"/>
        </statistics>
      </team>
    </season>
    <season id="24a0d0d7-2ba8-4edb-9354-d218e87e027e" year="2021" type="PST">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="6" games_started="6" minutes="184.0" field_goals_made="20" field_goals_att="55" field_goals_pct="0.364" two_points_made="7" two_points_att="23" two_points_pct="0.304" three_points_made="13" three_points_att="32" three_points_pct="0.406" blocked_att="3" free_throws_made="15" free_throws_att="16" free_throws_pct="0.938" offensive_rebounds="2" defensive_rebounds="13" rebounds="15" assists="2" turnovers="9" assists_turnover_ratio="0.22" steals="6" blocks="4" personal_fouls="9" tech_fouls="0" points="68" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="62.04" true_shooting_pct="0.548" efficiency="50" field_goals_at_rim_made="0" field_goals_at_rim_att="0" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="0" field_goals_at_midrange_att="0" field_goals_at_midrange_pct="0.0" usage_pct="19.78"/>
          <average minutes="30.7" points="11.3" off_rebounds="0.33" def_rebounds="2.17" rebounds="2.5" assists="0.3" steals="1.0" blocks="0.67" turnovers="1.5" personal_fouls="1.5" flagrant_fouls="0.0" blocked_att="0.5" field_goals_made="3.33" field_goals_att="9.17" three_points_made="2.17" three_points_att="5.33" free_throws_made="2.5" free_throws_att="2.67" two_points_made="1.17" two_points_att="3.83" efficiency="8.33" true_shooting_att="10.34"/>
        </statistics>
      </team>
    </season>
    <season id="e632f0e4-ea16-4dc1-b99e-af0e9d05ad7a" year="2021" type="CT">
      <team id="6e0c5edc-4a6d-416b-9e10-7cccf13e971f" name="Huskies" market="UConn" alias="CONN">
        <statistics>
          <total games_played="0" games_started="0" minutes="0.0" field_goals_made="0" field_goals_att="0" field_goals_pct="0.0" two_points_made="0" two_points_att="0" two_points_pct="0.0" three_points_made="0" three_points_att="0" three_points_pct="0.0" blocked_att="0" free_throws_made="0" free_throws_att="0" free_throws_pct="0.0" offensive_rebounds="0" defensive_rebounds="0" rebounds="0" assists="0" turnovers="0" assists_turnover_ratio="0.0" steals="0" blocks="0" personal_fouls="0" tech_fouls="0" points="0" flagrant_fouls="0" ejections="0" foulouts="0" true_shooting_att="0.0" true_shooting_pct="0" efficiency="0" field_goals_at_rim_made="0" field_goals_at_rim_att="0" field_goals_at_rim_pct="0.0" field_goals_at_midrange_made="0" field_goals_at_midrange_att="0" field_goals_at_midrange_pct="0.0" usage_pct="0"/>
          <average minutes="0.0" points="0.0" off_rebounds="0.0" def_rebounds="0.0" rebounds="0.0" assists="0.0" steals="0.0" blocks="0.0" turnovers="0.0" personal_fouls="0.0" flagrant_fouls="0.0" blocked_att="0.0" field_goals_made="0.0" field_goals_att="0.0" three_points_made="0.0" three_points_att="0.0" free_throws_made="0.0" free_throws_att="0.0" two_points_made="0.0" two_points_att="0.0" efficiency="0.0" true_shooting_att="0.0"/>
        </statistics>
      </team>
    </season>
  </seasons>
</player>
```