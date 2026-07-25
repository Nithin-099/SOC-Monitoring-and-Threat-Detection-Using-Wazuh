<!-- Custom Wazuh Detection Rules -->
<!-- Author: NithinAvula -->
<!-- Date: July 2026 -->

<group name="custom_detections,">

  <rule id="100001" level="15">
    <if_group>sysmon</if_group>
    <field name="win.eventdata.targetImage"
           type="pcre2">(?i)lsass.exe</field>
    <description>CUSTOM: LSASS access detected
    - Possible credential dumping
    (T1003.001)</description>
    <mitre>
      <id>T1003.001</id>
    </mitre>
  </rule>

  <rule id="100002" level="12">
    <if_group>sysmon</if_group>
    <field name="win.eventdata.commandLine"
           type="pcre2">(?i)mimikatz|sekurlsa|lsadump</field>
    <description>CUSTOM: Mimikatz keyword
    detected (T1003.001)</description>
    <mitre>
      <id>T1003.001</id>
    </mitre>
  </rule>

  <rule id="100003" level="12">
    <if_group>sysmon</if_group>
    <field name="win.eventdata.commandLine"
           type="pcre2">(?i)-enc|-encodedcommand|-ep bypass</field>
    <description>CUSTOM: Encoded PowerShell
    detected (T1059.001)</description>
    <mitre>
      <id>T1059.001</id>
    </mitre>
  </rule>

  <rule id="100004" level="10">
    <if_group>sysmon</if_group>
    <field name="win.eventdata.commandLine"
           type="pcre2">(?i)schtasks.*create|at\.exe</field>
    <description>CUSTOM: Scheduled task
    created (T1053.005)</description>
    <mitre>
      <id>T1053.005</id>
    </mitre>
  </rule>

  <rule id="100005" level="8">
    <if_group>sysmon</if_group>
    <field name="win.eventdata.commandLine"
           type="pcre2">(?i)net user|net localgroup|whoami /all</field>
    <description>CUSTOM: Account enumeration
    detected (T1087.001)</description>
    <mitre>
      <id>T1087.001</id>
    </mitre>
  </rule>

</group>
