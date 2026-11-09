# CHANAKYA analysis report

- Run: `run-20261109T090242449010Z-234d7e4473`
- Status: `COMPLETE`
- Repository: `JavaSecLab` (public, deliberately vulnerable teaching app)
- Revision/content hash: `dfa7a8dacae1de698a812053bca08ec1d373e88b`
- Provider/model: `none` / `none`
- Budget: `smoke`

## Findings


### idor

- Vulnerability class: `idor`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/MyBatisController.java", "class_name": "MyBatisController", "method_signature": "MyBatisController.safe1(String, Integer, String, String) -> R", "line_start": 46, "line_end": 104}, {"file_path": "src/main/java/top/whgojp/modules/sqli/service/impl/SqliServiceImpl.java", "class_name": "SqliServiceImpl", "method_signature": "SqliServiceImpl.nativeDelete(Integer) -> int", "line_start": 32, "line_end": 32}]`
- Affected path: `{"source_id": "15da427d8dff2ca3", "sink_id": "9db7f756dd39375e", "capability_id": null}`
- Why it matters: non_binding_guard
- Deterministic evidence: `["programmatic: (id == null)", "url_rule: route policy UNKNOWN", "object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### idor

- Vulnerability class: `idor`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe2(String, String, String, String) -> R", "line_start": 401, "line_end": 469}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe2(String, String, String, String) -> R", "line_start": 453, "line_end": 453}]`
- Affected path: `{"source_id": "6d5bfc274179ddfa", "sink_id": "b9fd544f7d0abf63", "capability_id": null}`
- Why it matters: non_binding_guard
- Deterministic evidence: `["url_rule: route policy UNKNOWN", "object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### idor

- Vulnerability class: `idor`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe2(String, String, String, String) -> R", "line_start": 401, "line_end": 469}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe2(String, String, String, String) -> R", "line_start": 437, "line_end": 437}]`
- Affected path: `{"source_id": "6d5bfc274179ddfa", "sink_id": "237e6b722f572332", "capability_id": null}`
- Why it matters: non_binding_guard
- Deterministic evidence: `["url_rule: route policy UNKNOWN", "object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### idor

- Vulnerability class: `idor`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/xss/controller/StoreController.java", "class_name": "StoreController", "method_signature": "StoreController.deleteOne(int) -> R", "line_start": 75, "line_end": 81}, {"file_path": "src/main/java/top/whgojp/modules/xss/service/impl/XssServiceImpl.java", "class_name": "XssServiceImpl", "method_signature": "XssServiceImpl.deleteById(int) -> int", "line_start": 51, "line_end": 51}]`
- Affected path: `{"source_id": "fa09e0abb1a73ebb", "sink_id": "e24dd0636c103baf", "capability_id": null}`
- Why it matters: non_binding_guard
- Deterministic evidence: `["programmatic: (xssService.deleteById(id)==1)", "url_rule: route policy UNKNOWN", "object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### idor

- Vulnerability class: `idor`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/MyBatisController.java", "class_name": "MyBatisController", "method_signature": "MyBatisController.safe1(String, Integer, String, String) -> R", "line_start": 46, "line_end": 104}, {"file_path": "src/main/java/top/whgojp/modules/sqli/service/impl/SqliServiceImpl.java", "class_name": "SqliServiceImpl", "method_signature": "SqliServiceImpl.nativeSelect(Integer) -> Sqli", "line_start": 43, "line_end": 43}]`
- Affected path: `{"source_id": "15da427d8dff2ca3", "sink_id": "88418c8067eba4da", "capability_id": null}`
- Why it matters: non_binding_guard
- Deterministic evidence: `["programmatic: (id != null)", "programmatic: (sqliService.nativeSelect(id) != null)", "url_rule: route policy UNKNOWN", "object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 165, "line_end": 243}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 191, "line_end": 191}]`
- Affected path: `{"source_id": "530e3db6a4b7efe7", "sink_id": "51c7280a77d8aa36", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 165, "line_end": 243}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 191, "line_end": 191}]`
- Affected path: `{"source_id": "530e3db6a4b7efe7", "sink_id": "51c7280a77d8aa36", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 245, "line_end": 310}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 281, "line_end": 281}]`
- Affected path: `{"source_id": "67ec4acc85d89810", "sink_id": "4012e13955aaa868", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 67, "line_end": 156}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 121, "line_end": 121}]`
- Affected path: `{"source_id": "074199f4090d3674", "sink_id": "709858ff498fb7ab", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 67, "line_end": 156}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 121, "line_end": 121}]`
- Affected path: `{"source_id": "074199f4090d3674", "sink_id": "709858ff498fb7ab", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 67, "line_end": 156}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 121, "line_end": 121}]`
- Affected path: `{"source_id": "074199f4090d3674", "sink_id": "709858ff498fb7ab", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 67, "line_end": 156}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 100, "line_end": 100}]`
- Affected path: `{"source_id": "074199f4090d3674", "sink_id": "726d84b00af98bf2", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 67, "line_end": 156}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 100, "line_end": 100}]`
- Affected path: `{"source_id": "074199f4090d3674", "sink_id": "726d84b00af98bf2", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 245, "line_end": 310}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 294, "line_end": 294}]`
- Affected path: `{"source_id": "67ec4acc85d89810", "sink_id": "30b65b37e2c78ef8", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 165, "line_end": 243}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 211, "line_end": 211}]`
- Affected path: `{"source_id": "530e3db6a4b7efe7", "sink_id": "7829bee47ba0ac80", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 165, "line_end": 243}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 211, "line_end": 211}]`
- Affected path: `{"source_id": "530e3db6a4b7efe7", "sink_id": "7829bee47ba0ac80", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 165, "line_end": 243}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 211, "line_end": 211}]`
- Affected path: `{"source_id": "530e3db6a4b7efe7", "sink_id": "7829bee47ba0ac80", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 67, "line_end": 156}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 131, "line_end": 131}]`
- Affected path: `{"source_id": "67e985cded473f66", "sink_id": "eb634b6cdd8b2114", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/MyBatisController.java", "class_name": "MyBatisController", "method_signature": "MyBatisController.special3In(String, String) -> R", "line_start": 254, "line_end": 289}, {"file_path": "src/main/java/top/whgojp/modules/sqli/service/impl/SqliServiceImpl.java", "class_name": "SqliServiceImpl", "method_signature": "SqliServiceImpl.inVul(String) -> List<Sqli>", "line_start": 94, "line_end": 94}]`
- Affected path: `{"source_id": "1d17029eb6daf737", "sink_id": "341a919c315e26d2", "capability_id": null}`
- Why it matters: mybatis_dollar_interpolation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 471, "line_end": 563}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 514, "line_end": 514}]`
- Affected path: `{"source_id": "6b954d60abf6cd72", "sink_id": "b00ea6c0313f378a", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 67, "line_end": 156}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul1(String, String, String, String) -> R", "line_start": 110, "line_end": 110}]`
- Affected path: `{"source_id": "67e985cded473f66", "sink_id": "d905e38328c93daa", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 471, "line_end": 563}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 500, "line_end": 500}]`
- Affected path: `{"source_id": "026d129ff8fd7a03", "sink_id": "56b1e131cbf7cb4e", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 471, "line_end": 563}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 500, "line_end": 500}]`
- Affected path: `{"source_id": "026d129ff8fd7a03", "sink_id": "56b1e131cbf7cb4e", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.special1OrderBy(String, String) -> R", "line_start": 653, "line_end": 741}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.special1OrderBy(String, String) -> R", "line_start": 719, "line_end": 719}]`
- Affected path: `{"source_id": "9d674e40dc91de7a", "sink_id": "29b30e5bab6bcda1", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 471, "line_end": 563}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 528, "line_end": 528}]`
- Affected path: `{"source_id": "026d129ff8fd7a03", "sink_id": "ee12e976cbca13d3", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 471, "line_end": 563}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 528, "line_end": 528}]`
- Affected path: `{"source_id": "026d129ff8fd7a03", "sink_id": "ee12e976cbca13d3", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 471, "line_end": 563}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 528, "line_end": 528}]`
- Affected path: `{"source_id": "026d129ff8fd7a03", "sink_id": "ee12e976cbca13d3", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.special1OrderBy(String, String) -> R", "line_start": 653, "line_end": 741}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.special1OrderBy(String, String) -> R", "line_start": 676, "line_end": 676}]`
- Affected path: `{"source_id": "9d674e40dc91de7a", "sink_id": "5a88e2c6f921d756", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.special3Limit(String, String) -> R", "line_start": 816, "line_end": 885}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.special3Limit(String, String) -> R", "line_start": 835, "line_end": 835}]`
- Affected path: `{"source_id": "58fff946bb3fd3c5", "sink_id": "7b74ec9b44b6e1af", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 245, "line_end": 310}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 274, "line_end": 274}]`
- Affected path: `{"source_id": "ac4135841d435cb1", "sink_id": "0bdee2c5947b105e", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 245, "line_end": 310}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 274, "line_end": 274}]`
- Affected path: `{"source_id": "ac4135841d435cb1", "sink_id": "0bdee2c5947b105e", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/MyBatisController.java", "class_name": "MyBatisController", "method_signature": "MyBatisController.special2Like(String, String) -> R", "line_start": 222, "line_end": 252}, {"file_path": "src/main/java/top/whgojp/modules/sqli/service/impl/SqliServiceImpl.java", "class_name": "SqliServiceImpl", "method_signature": "SqliServiceImpl.likeVul(String) -> List<Sqli>", "line_start": 84, "line_end": 84}]`
- Affected path: `{"source_id": "bae37d6682f1418d", "sink_id": "0010adfdbe4bd1a8", "capability_id": null}`
- Why it matters: mybatis_dollar_interpolation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/MyBatisController.java", "class_name": "MyBatisController", "method_signature": "MyBatisController.special1OrderBy(String, String) -> R", "line_start": 168, "line_end": 206}, {"file_path": "src/main/java/top/whgojp/modules/sqli/service/impl/SqliServiceImpl.java", "class_name": "SqliServiceImpl", "method_signature": "SqliServiceImpl.orderByVul(String) -> List<Sqli>", "line_start": 69, "line_end": 69}]`
- Affected path: `{"source_id": "ad73d01dca883494", "sink_id": "44d4d5d71a74bc37", "capability_id": null}`
- Why it matters: mybatis_dollar_interpolation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 471, "line_end": 563}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.safe3(String, String, String, String) -> R", "line_start": 542, "line_end": 542}]`
- Affected path: `{"source_id": "6b954d60abf6cd72", "sink_id": "20fefc79c78859ef", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 165, "line_end": 243}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 201, "line_end": 201}]`
- Affected path: `{"source_id": "9766f982a3cf3739", "sink_id": "f22c2057c33080e7", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 165, "line_end": 243}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul2(String, String, String, String) -> R", "line_start": 221, "line_end": 221}]`
- Affected path: `{"source_id": "9766f982a3cf3739", "sink_id": "4d0bce9dff0b08db", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 245, "line_end": 310}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 288, "line_end": 288}]`
- Affected path: `{"source_id": "ac4135841d435cb1", "sink_id": "64710d6b6d8016df", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 245, "line_end": 310}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 288, "line_end": 288}]`
- Affected path: `{"source_id": "ac4135841d435cb1", "sink_id": "64710d6b6d8016df", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 245, "line_end": 310}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.vul3(String, String, String, String) -> R", "line_start": 288, "line_end": 288}]`
- Affected path: `{"source_id": "ac4135841d435cb1", "sink_id": "64710d6b6d8016df", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### sql_injection

- Vulnerability class: `sql_injection`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.special2Like(String, String) -> R", "line_start": 743, "line_end": 814}, {"file_path": "src/main/java/top/whgojp/modules/sqli/controller/JdbcController.java", "class_name": "JdbcController", "method_signature": "JdbcController.special2Like(String, String) -> R", "line_start": 767, "line_end": 767}]`
- Affected path: `{"source_id": "b7a5e2354a9eb283", "sink_id": "391369a25019263c", "capability_id": null}`
- Why it matters: sql_concatenation
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### insecure_deserialization

- Vulnerability class: `insecure_deserialization`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/deserialize/readobject/controller/ReadObjectController.java", "class_name": "ReadObjectController", "method_signature": "ReadObjectController.vul(String) -> R", "line_start": 59, "line_end": 75}, {"file_path": "src/main/java/top/whgojp/modules/deserialize/readobject/controller/ReadObjectController.java", "class_name": "ReadObjectController", "method_signature": "ReadObjectController.vul(String) -> R", "line_start": 67, "line_end": 67}]`
- Affected path: `{"source_id": "f6594a1cbb809d65", "sink_id": "1bc7ff9792cc1de7", "capability_id": null}`
- Why it matters: deserialization_no_filter
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### insecure_deserialization

- Vulnerability class: `insecure_deserialization`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/components/xstream/controller/XstreamController.java", "class_name": "XstreamController", "method_signature": "XstreamController.vul(String) -> String", "line_start": 50, "line_end": 67}, {"file_path": "src/main/java/top/whgojp/modules/components/xstream/controller/XstreamController.java", "class_name": "XstreamController", "method_signature": "XstreamController.vul(String) -> String", "line_start": 59, "line_end": 59}]`
- Affected path: `{"source_id": "26d13dd3abd59c94", "sink_id": "6c94c0da985c5116", "capability_id": null}`
- Why it matters: xstream_no_allowlist
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### insecure_deserialization

- Vulnerability class: `insecure_deserialization`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/deserialize/xmldecoder/controller/XMLDecoderController.java", "class_name": "XMLDecoderController", "method_signature": "XMLDecoderController.vul(String) -> R", "line_start": 46, "line_end": 70}, {"file_path": "src/main/java/top/whgojp/modules/deserialize/xmldecoder/controller/XMLDecoderController.java", "class_name": "XMLDecoderController", "method_signature": "XMLDecoderController.vul(String) -> R", "line_start": 64, "line_end": 64}]`
- Affected path: `{"source_id": "e213f01150818b54", "sink_id": "fc03f202c2869192", "capability_id": null}`
- Why it matters: deserialization_no_filter
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### insecure_deserialization

- Vulnerability class: `insecure_deserialization`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/components/xstream/controller/XstreamController.java", "class_name": "XstreamController", "method_signature": "XstreamController.safe1(String) -> String", "line_start": 69, "line_end": 85}, {"file_path": "src/main/java/top/whgojp/modules/components/xstream/controller/XstreamController.java", "class_name": "XstreamController", "method_signature": "XstreamController.safe1(String) -> String", "line_start": 79, "line_end": 79}]`
- Affected path: `{"source_id": "b9371aa45b5625b5", "sink_id": "3b42ba87e6c24931", "capability_id": null}`
- Why it matters: xstream_no_allowlist
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### insecure_deserialization

- Vulnerability class: `insecure_deserialization`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/deserialize/readobject/controller/ReadObjectController.java", "class_name": "ReadObjectController", "method_signature": "ReadObjectController.safe1(String) -> R", "line_start": 79, "line_end": 94}, {"file_path": "src/main/java/top/whgojp/modules/deserialize/readobject/controller/ReadObjectController.java", "class_name": "ReadObjectController", "method_signature": "ReadObjectController.safe1(String) -> R", "line_start": 87, "line_end": 87}]`
- Affected path: `{"source_id": "4f9e64e5bbf4d235", "sink_id": "da10c82f5226e42c", "capability_id": null}`
- Why it matters: deserialization_no_filter
- Deterministic evidence: `["object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

### insecure_deserialization

- Vulnerability class: `insecure_deserialization`
- Evidence quality: `VALIDATED`
- Files/symbols: `[{"file_path": "src/main/java/top/whgojp/modules/components/jackson/controller/JacksonController.java", "class_name": "JacksonController", "method_signature": "JacksonController.vul(String) -> String", "line_start": 39, "line_end": 56}, {"file_path": "src/main/java/top/whgojp/modules/components/jackson/controller/JacksonController.java", "class_name": "JacksonController", "method_signature": "JacksonController.vul(String) -> String", "line_start": 50, "line_end": 50}]`
- Affected path: `{"source_id": "57e0b5705f2a08f7", "sink_id": "e2247b702a61cc6d", "capability_id": null}`
- Why it matters: jackson_default_typing_enabled
- Deterministic evidence: `["jackson_default_typing: mapper.enableDefaultTyping()", "object_access_static_verdict"]`
- AI inference: `[]`
- Contradictions: `[]`
- Uncertainty: `[]`

## Unresolved

11 item(s).
- `UNCERTAIN` sensitive_effect_authorization_review: sensitive_effect_authorization_unresolved
- `UNCERTAIN` sensitive_effect_authorization_review: sensitive_effect_authorization_unresolved
- `UNCERTAIN` sensitive_effect_authorization_review: sensitive_effect_authorization_unresolved
- `UNCERTAIN` sensitive_effect_authorization_review: sensitive_effect_authorization_unresolved
- `UNCERTAIN` sensitive_effect_authorization_review: sensitive_effect_authorization_unresolved
- `UNCERTAIN` sensitive_effect_authorization_review: sensitive_effect_authorization_unresolved
- `UNCERTAIN` sensitive_effect_authorization_review: sensitive_effect_authorization_unresolved
- `UNCERTAIN` sensitive_effect_authorization_review: sensitive_effect_authorization_unresolved
- `UNCERTAIN` sql_injection: sql_ambiguous_taint
- `UNCERTAIN` sql_injection: sql_ambiguous_taint
- `UNCERTAIN` insecure_deserialization: jackson_default_typing_not_proven

## AI final review

No terminal AI review result was produced.

## Unsupported

1 item(s).
- `PROGRAM_EVIDENCE_LIMITATION`: Bounded ProgramIndex evidence queries are available; broader arbitrary query-specific ProgramEvidence expansion remains unsupported where the existing port reports it.

## Telemetry summary

```json
{
  "cached_tokens": null,
  "calls": 0,
  "cost_status": null,
  "duration_ms": null,
  "estimated_cost_usd": null,
  "input_tokens": null,
  "output_tokens": null,
  "provider": null,
  "provider_error_count": 0,
  "requested_model_profile_id": null,
  "returned_provider_model_id": null,
  "total_tokens": null
}
```
