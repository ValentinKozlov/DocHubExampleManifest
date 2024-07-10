### Расчет доли "здоровых" систем

{{#unit_statistics}}

**{{tu_block}}**
- Общее количество систем: {{total}}
    - *Внутренних систем:* {{internal}}
    - *Внешних систем:* {{external}}

- Рейтинги здоровья внутренних {{internal}} систем:
{{#ratings}}
    - `{{rating}}` ({{title}}): **{{count}} ({{cover}} %)**{{#default_count}}; *{{default_count}} заполнено оценками по-умолчанию*{{/default_count}}
{{/ratings}}

{{detailed_sys_link}}
{{/unit_statistics}}