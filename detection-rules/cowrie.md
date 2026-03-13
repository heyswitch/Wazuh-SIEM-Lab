<group name="cowrie">
 <rule id="100300" level="8">
   <field name="eventid">cowrie.login.success</field>
   <description>Successful Cowrie SSH login detected</description>
 </rule>

 <rule id="100301" level="3">
   <field name="eventid">cowrie.login.failed</field>
   <description>Failed Cowrie SSH login detected</description>
 </rule>

 <rule id="100302" level="13">
   <field name="eventid">cowrie.command.input</field>
   <description>Cowrie command input detected</description>
 </rule>
</group>