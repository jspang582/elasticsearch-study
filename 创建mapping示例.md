```json
PUT /XXX/_doc/_mapping
{
	"properties": {
		"name": {
			"type": "text",
			"fields": {
				"keyword": {
					"type": "keyword"
				},
				"pinyin": {
					"type": "text",
					"analyzer": "pinyin_analyzer"
				},
				"suggest": {
					"type": "completion",
					"analyzer": "pinyin_analyzer_suggest",
					"search_analyzer": "pinyin_analyzer_suggest_no_first_letter",
					"preserve_separators": true,
					"preserve_position_increments": true,
					"max_input_length": 50
				}
			},
			"analyzer": "ik_max_word"
		}
	}
}
```

