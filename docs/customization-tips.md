# 🎨 Dicas de Personalização

Guia completo para adaptar e personalizar workflows n8n para suas necessidades específicas.

---

## 🎯 Por Que Personalizar?

### 🎨 Benefícios da Personalização

- **📈 Melhor Performance** - Otimizado para seu caso de uso
- **🎯 Maior Precisão** - Filtros específicos para seus dados
- **💼 Identidade da Marca** - Templates personalizados
- **⚡ Eficiência** - Fluxos adaptados ao seu processo
- **🔄 Escalabilidade** - Cresce com suas necessidades

---

## 🛠️ Áreas de Personalização

### 📝 Templates de Mensagem

#### 📧 Email Personalizado

```json
{
  "subject": "{{ $json.clinic_name }} - Confirmação de Consulta",
  "body": "Olá {{ $json.patient_name }},\n\nSua consulta foi confirmada para {{ $json.appointment_date }} às {{ $json.appointment_time }}.\n\nLocal: {{ $json.clinic_address }}\nDoutor: {{ $json.doctor_name }}\n\nAtenciosamente,\n{{ $json.clinic_name }}"
}
```

#### 📱 WhatsApp Template

```json
{
  "message": "🦷 *{{ $json.clinic_name }}*\n\nOlá {{ $json.patient_name }}!\n\n✅ Sua consulta foi confirmada:\n📅 Data: {{ $json.appointment_date }}\n⏰ Horário: {{ $json.appointment_time }}\n👨‍⚕️ Doutor: {{ $json.doctor_name }}\n📍 Endereço: {{ $json.clinic_address }}\n\n📞 Para reagendar: {{ $json.phone }}\n🌐 Site: {{ $json.website }}"
}
```

### 🎨 Branding e Identidade Visual

#### 🎯 Cores da Marca

```css
/* Variáveis CSS para sua marca */
:root {
  --primary-color: #2563eb;
  --secondary-color: #7c3aed;
  --accent-color: #f59e0b;
  --text-color: #1f2937;
  --background-color: #f9fafb;
}
```

#### 📋 Templates HTML

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>{{ clinic_name }} - Confirmação</title>
    <style>
        .header { background-color: {{ brand_color }}; }
        .footer { background-color: {{ brand_color }}; }
    </style>
</head>
<body>
    <div class="header">
        <img src="{{ logo_url }}" alt="{{ clinic_name }}">
    </div>
    <div class="content">
        {{ message_content }}
    </div>
    <div class="footer">
        <p>{{ clinic_name }} - {{ address }}</p>
    </div>
</body>
</html>
```

---

## 🔧 Configurações Avançadas

### ⏰ Agendamento Inteligente

#### 📅 Horários de Funcionamento

```json
{
  "business_hours": {
    "monday": {"start": "08:00", "end": "18:00"},
    "tuesday": {"start": "08:00", "end": "18:00"},
    "wednesday": {"start": "08:00", "end": "18:00"},
    "thursday": {"start": "08:00", "end": "18:00"},
    "friday": {"start": "08:00", "end": "17:00"},
    "saturday": {"start": "08:00", "end": "12:00"},
    "sunday": {"closed": true}
  }
}
```

#### 🚫 Feriados e Exceções

```json
{
  "holidays": [
    "2024-01-01",
    "2024-04-21",
    "2024-09-07",
    "2024-12-25"
  ],
  "special_schedules": {
    "2024-12-24": {"start": "08:00", "end": "12:00"},
    "2024-12-31": {"start": "08:00", "end": "12:00"}
  }
}
```

### 🎯 Filtros Personalizados

#### 📊 Critérios de Agendamento

```javascript
// Filtro para pacientes VIP
if ($json.patient_type === "vip") {
  return {
    priority: "high",
    reminder_hours: 24,
    confirmation_required: true
  };
}

// Filtro para consultas de emergência
if ($json.appointment_type === "emergency") {
  return {
    priority: "urgent",
    reminder_hours: 2,
    auto_confirm: true
  };
}
```

---

## 🔄 Automações Inteligentes

### 🤖 IA Personalizada

#### 📝 Prompts Customizados

```json
{
  "prompt": "Você é um assistente virtual da clínica {{ clinic_name }}. Responda de forma profissional e amigável, sempre mencionando nossa especialidade em {{ specialty }}. Use o tom de voz {{ tone }} e inclua informações sobre {{ services }}."
}
```

#### 🎯 Análise de Sentimento

```javascript
// Análise de feedback do paciente
const sentiment = await analyzeSentiment($json.feedback);
if (sentiment.score < 0.3) {
  // Feedback negativo - escalar para gerente
  await escalateToManager($json);
} else if (sentiment.score > 0.7) {
  // Feedback positivo - agradecer
  await sendThankYouMessage($json);
}
```

### 📊 Relatórios Personalizados

#### 📈 Métricas de Negócio

```json
{
  "metrics": {
    "daily_appointments": "COUNT(appointments WHERE date = TODAY)",
    "cancellation_rate": "COUNT(cancelled) / COUNT(total) * 100",
    "patient_satisfaction": "AVG(satisfaction_scores)",
    "revenue_daily": "SUM(appointment_values WHERE date = TODAY)"
  }
}
```

#### 📋 Dashboards Customizados

```javascript
// Geração de relatório diário
const dailyReport = {
  date: new Date().toISOString().split('T')[0],
  appointments: await getAppointmentsCount(),
  cancellations: await getCancellationsCount(),
  revenue: await calculateDailyRevenue(),
  topDoctors: await getTopPerformingDoctors(),
  patientFeedback: await getRecentFeedback()
};
```

---

## 🎨 Personalização Visual

### 🎨 Temas e Cores

#### 🌈 Paleta de Cores

```json
{
  "themes": {
    "default": {
      "primary": "#2563eb",
      "secondary": "#7c3aed",
      "success": "#10b981",
      "warning": "#f59e0b",
      "error": "#ef4444"
    },
    "dental": {
      "primary": "#0891b2",
      "secondary": "#0e7490",
      "accent": "#06b6d4"
    },
    "corporate": {
      "primary": "#1f2937",
      "secondary": "#374151",
      "accent": "#6b7280"
    }
  }
}
```

### 📱 Responsividade

#### 📱 Mobile-First Design

```css
/* Estilos responsivos para emails */
@media only screen and (max-width: 600px) {
  .container {
    width: 100% !important;
    padding: 10px !important;
  }
  
  .header img {
    width: 200px !important;
    height: auto !important;
  }
  
  .button {
    width: 100% !important;
    text-align: center !important;
  }
}
```

---

## 🔧 Configurações Técnicas

### ⚡ Performance

#### 🚀 Otimizações

```javascript
// Cache de dados frequentes
const cacheKey = `appointments_${date}`;
let appointments = await cache.get(cacheKey);
if (!appointments) {
  appointments = await fetchAppointments(date);
  await cache.set(cacheKey, appointments, 300); // 5 minutos
}
```

#### 📊 Monitoramento

```json
{
  "monitoring": {
    "execution_time_threshold": 5000,
    "error_rate_threshold": 0.05,
    "success_rate_target": 0.95,
    "alert_channels": ["email", "slack", "sms"]
  }
}
```

### 🔒 Segurança

#### 🛡️ Validação de Dados

```javascript
// Validação de entrada
function validateAppointmentData(data) {
  const required = ['patient_name', 'appointment_date', 'doctor_id'];
  const missing = required.filter(field => !data[field]);
  
  if (missing.length > 0) {
    throw new Error(`Campos obrigatórios: ${missing.join(', ')}`);
  }
  
  // Validação de data
  const appointmentDate = new Date(data.appointment_date);
  if (appointmentDate < new Date()) {
    throw new Error('Data de consulta não pode ser no passado');
  }
  
  return true;
}
```

---

## 📚 Exemplos Práticos

### 🦷 Consultório Odontológico

#### 📅 Agendamento Inteligente

```json
{
  "workflow": "dental-appointment-automation",
  "customizations": {
    "clinic_name": "Clínica Sorriso Perfeito",
    "specialties": ["Ortodontia", "Implantes", "Clareamento"],
    "appointment_duration": 60,
    "buffer_time": 15,
    "reminder_times": [24, 2, 1],
    "cancellation_policy": "Até 24h antes"
  }
}
```

### 📱 Redes Sociais

#### 📲 Postagens Automáticas

```json
{
  "workflow": "social-media-automation",
  "customizations": {
    "brand_voice": "Profissional e amigável",
    "posting_schedule": {
      "monday": ["09:00", "15:00"],
      "wednesday": ["10:00", "16:00"],
      "friday": ["11:00", "17:00"]
    },
    "hashtags": ["#odontologia", "#saúde", "#sorriso"],
    "content_categories": ["Dicas", "Casos", "Promoções"]
  }
}
```

---

## 💡 Dicas Pro

### 🎯 Personalização Eficiente

- **📋 Documente** suas customizações
- **🔄 Versionamento** de configurações
- **🧪 Teste** em ambiente de desenvolvimento
- **📊 Monitore** performance após mudanças
- **🔄 Iteração** baseada em feedback

### 🚀 Melhores Práticas

- **🎨 Consistência** visual em todos os templates
- **📱 Responsividade** para todos os dispositivos
- **⚡ Performance** otimizada
- **🔒 Segurança** em todas as integrações
- **📈 Escalabilidade** para crescimento futuro

---

<div align="center">

**🎨 Personalize com criatividade e mantenha a qualidade!**

</div>
