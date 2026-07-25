<script setup lang="ts">
import { Building2, CheckCircle2, ClipboardList, Clock3, Factory, Globe2, Radio, Send } from 'lucide-vue-next'
import { type LocaleText, usePageSeo } from '~/data/site'

const { locale } = useI18n()

const title: LocaleText = { zh: '联系我们', en: 'Contact Us' }
const description: LocaleText = {
  zh: '三地协同服务项目对接，您可以在这里了解联系信息，也可以提交业务咨询。',
  en: 'Three-city coordination for project discussions, contact information and business inquiries.'
}

usePageSeo(title, description)

const form = reactive({
  name: '',
  phone: '',
  email: '',
  company: '',
  message: ''
})
const submitted = ref(false)

const text = (value: LocaleText) => locale.value === 'en' ? value.en : value.zh

const sections = [
  { id: 'info', label: { zh: '联系方式', en: 'Contact Info' } },
  { id: 'inquiry', label: { zh: '业务咨询', en: 'Business Inquiry' } }
]

const contacts = [
  {
    icon: Building2,
    title: { zh: '杭州总部', en: 'Hangzhou Headquarters' },
    text: { zh: '负责公司运营、客户沟通与项目统筹。', en: 'Operations, client communication and project coordination.' }
  },
  {
    icon: Factory,
    title: { zh: '深圳量产中心', en: 'Shenzhen Production Center' },
    text: { zh: '负责批量制造、交付协同与供应链支持。', en: 'Mass production, delivery coordination and supply chain support.' }
  },
  {
    icon: Radio,
    title: { zh: '上海研发中心', en: 'Shanghai R&D Center' },
    text: { zh: '支持固件开发、无线性能测试与客户工程对接。', en: 'Firmware development, wireless performance testing and client engineering support.' }
  },
  {
    icon: Clock3,
    title: { zh: '工作时间', en: 'Business Hours' },
    text: { zh: '工作日 09:00 - 18:00。', en: 'Weekdays, 09:00 - 18:00.' }
  }
]

const inquiryPoints = [
  {
    icon: ClipboardList,
    value: {
      zh: 'PCB 打样、小批量与批量生产需求',
      en: 'PCB prototypes, small batches and volume production'
    }
  },
  {
    icon: Factory,
    value: {
      zh: 'SMT 贴片、组装测试与交付计划',
      en: 'SMT assembly, box-build testing and delivery planning'
    }
  },
  {
    icon: Globe2,
    value: {
      zh: '元器件采购、BOM 评估与供应链配套',
      en: 'Component sourcing, BOM review and supply chain support'
    }
  }
]

function submitInquiry() {
  submitted.value = true
}
</script>

<template>
  <div class="contact-page">
    <section class="contact-hero">
      <div class="shell contact-hero-inner">
        <p class="eyebrow">{{ locale === 'en' ? 'Contact YiYuanLi' : '联系壹原理' }}</p>
        <h1>{{ text(title) }}</h1>
        <p>{{ text(description) }}</p>
      </div>
    </section>

    <SectionAnchorNav :items="sections" :label="locale === 'en' ? 'Contact sections' : '联系我们页面导航'" />

    <section id="info" class="contact-section">
      <div class="shell">
        <div class="contact-heading">
          <p class="eyebrow">{{ locale === 'en' ? 'Company Information' : '联系方式' }}</p>
          <h2>{{ locale === 'en' ? 'Three cities, one coordinated service path.' : '三地协同，统一对接项目需求。' }}</h2>
          <p>
            {{
              locale === 'en'
                ? 'Project details, visit arrangements and follow-up communication can be submitted through the business inquiry form below.'
                : '项目资料、来访安排与后续沟通，可通过下方业务咨询表单提交。'
            }}
          </p>
        </div>

        <div class="contact-grid">
          <article v-for="item in contacts" :key="text(item.title)">
            <component :is="item.icon" :size="24" aria-hidden="true" />
            <h3>{{ text(item.title) }}</h3>
            <p>{{ text(item.text) }}</p>
          </article>
        </div>
      </div>
    </section>

    <section id="inquiry" class="contact-section section-paper">
      <div class="shell">
        <div class="contact-heading">
          <p class="eyebrow">{{ locale === 'en' ? 'Business Inquiry' : '业务咨询' }}</p>
          <h2>{{ locale === 'en' ? 'Tell us what you are building and what support you need.' : '说明项目需求，我们会安排合适的人员跟进。' }}</h2>
          <p>
            {{
              locale === 'en'
                ? 'Share the product type, estimated quantity, delivery timeline or technical notes, and we will respond with the next step.'
                : '请留下产品类型、预计数量、交期要求或技术资料，我们会根据需求安排后续对接。'
            }}
          </p>
        </div>

        <div class="inquiry-panel">
          <aside class="inquiry-info">
            <h3>
              <span>{{ locale === 'en' ? 'Project' : '项目' }}</span>
              {{ locale === 'en' ? 'Consultation' : '咨询' }}
            </h3>
            <p>
              {{
                locale === 'en'
                  ? 'Use this form for manufacturing inquiries, quotation preparation and early technical communication.'
                  : '这个表单用于制造咨询、报价准备和前期技术沟通，请尽量填写关键项。'
              }}
            </p>

            <ul>
              <li v-for="item in inquiryPoints" :key="text(item.value)">
                <span class="inquiry-icon">
                  <component :is="item.icon" :size="19" aria-hidden="true" />
                </span>
                <span>{{ text(item.value) }}</span>
              </li>
            </ul>

          </aside>

          <form class="business-form" novalidate @submit.prevent="submitInquiry">
            <div class="field">
              <label for="contact-name">{{ locale === 'en' ? 'Name' : '姓名' }} *</label>
              <input id="contact-name" v-model="form.name" type="text" autocomplete="name" required>
            </div>
            <div class="field">
              <label for="contact-phone">{{ locale === 'en' ? 'Phone' : '电话' }} *</label>
              <input id="contact-phone" v-model="form.phone" type="tel" autocomplete="tel" required>
            </div>
            <div class="field">
              <label for="contact-email">Email</label>
              <input id="contact-email" v-model="form.email" type="email" autocomplete="email">
            </div>
            <div class="field">
              <label for="contact-company">{{ locale === 'en' ? 'Company' : '公司名称' }}</label>
              <input id="contact-company" v-model="form.company" type="text" autocomplete="organization">
            </div>
            <div class="field field-wide">
              <label for="contact-message">{{ locale === 'en' ? 'Inquiry Details' : '咨询内容' }} *</label>
              <textarea id="contact-message" v-model="form.message" rows="5" required />
            </div>

            <p v-if="submitted" class="form-success" role="status">
              <CheckCircle2 :size="18" aria-hidden="true" />
              {{ locale === 'en' ? 'Your inquiry has been recorded. We will contact you soon.' : '咨询已提交，我们会尽快与您联系。' }}
            </p>

            <button class="submit-button" type="submit">
              {{ locale === 'en' ? 'Submit Inquiry' : '提交咨询' }}
              <Send :size="16" aria-hidden="true" />
            </button>
          </form>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.contact-page {
  background: var(--white);
}

.contact-hero {
  background: var(--primary);
  color: var(--white);
}

.contact-hero-inner {
  min-height: 340px;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding: 78px 0 58px;
}

.contact-hero h1 {
  margin: 0;
  font-size: 42px;
  line-height: 1.18;
  font-weight: 750;
}

.contact-hero p:not(.eyebrow) {
  max-width: 660px;
  margin: 20px 0 0;
  color: rgba(255,255,255,0.8);
  font-size: 16px;
  line-height: 1.8;
}

.contact-section {
  padding: 88px 0;
  scroll-margin-top: 126px;
}

.section-paper {
  background: var(--paper);
}

.contact-heading {
  max-width: 760px;
  margin-bottom: 40px;
}

.contact-heading h2 {
  margin: 0;
  font-size: 34px;
  line-height: 1.28;
  font-weight: 750;
}

.contact-heading h2::after {
  content: "";
  display: block;
  width: 56px;
  height: 3px;
  margin-top: 16px;
  background: var(--accent);
}

.contact-heading > p:not(.eyebrow) {
  margin: 16px 0 0;
  color: var(--muted);
  font-size: 16px;
}

.contact-grid {
  display: grid;
  grid-template-columns: repeat(4,minmax(0,1fr));
  border-top: 1px solid var(--line);
  border-left: 1px solid var(--line);
}

.contact-grid article {
  min-height: 210px;
  padding: 26px 22px;
  border-right: 1px solid var(--line);
  border-bottom: 1px solid var(--line);
  background: var(--white);
}

.contact-grid svg {
  color: var(--accent-hover);
}

.contact-grid h3 {
  margin: 24px 0 8px;
  font-size: 18px;
}

.contact-grid p {
  margin: 0;
  color: var(--muted);
  font-size: 14px;
  line-height: 1.75;
}

.inquiry-panel {
  display: grid;
  grid-template-columns: 390px minmax(0, 1fr);
  min-height: 560px;
  border: 5px solid var(--primary);
  background: var(--white);
}

.inquiry-info {
  padding: 54px 38px;
  background: var(--primary);
  color: var(--white);
}

.inquiry-info h3 {
  margin: 0;
  font-size: 32px;
  line-height: 1.25;
  font-weight: 750;
}

.inquiry-info h3 span {
  color: var(--accent);
}

.inquiry-info > p {
  margin: 20px 0 28px;
  color: rgba(255,255,255,0.88);
  font-size: 15px;
  line-height: 1.8;
}

.inquiry-info ul {
  display: grid;
  gap: 20px;
  margin: 0;
  padding: 0;
  list-style: none;
}

.inquiry-info li {
  display: grid;
  grid-template-columns: 34px minmax(0, 1fr);
  align-items: center;
  gap: 14px;
  font-size: 15px;
  font-weight: 650;
  line-height: 1.55;
}

.inquiry-icon {
  width: 34px;
  height: 34px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border: 1px solid rgba(255,255,255,0.82);
  border-radius: 50%;
  color: rgba(255,255,255,0.9);
}

.business-form {
  display: grid;
  align-content: start;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 20px;
  padding: 54px;
}

.field {
  display: grid;
  gap: 7px;
}

.field-wide {
  grid-column: 1 / -1;
}

.field label {
  color: var(--primary);
  font-size: 14px;
  font-weight: 750;
}

.field input,
.field textarea {
  width: 100%;
  min-width: 0;
  border: 1px solid #e6e6e6;
  border-radius: 0;
  background: #fbfbfb;
  color: var(--ink);
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.field input {
  min-height: 56px;
  padding: 0 14px;
}

.field textarea {
  min-height: 132px;
  padding: 12px 14px;
  resize: vertical;
}

.field input:focus,
.field textarea:focus {
  border-color: var(--accent);
  box-shadow: 0 0 0 3px rgba(252,171,3,0.16);
  outline: none;
}

.form-success {
  grid-column: 1 / -1;
  display: flex;
  align-items: center;
  gap: 8px;
  margin: 0;
  color: #0f633c;
  font-size: 14px;
  font-weight: 700;
}

.submit-button {
  width: fit-content;
  min-height: 48px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  margin-top: 18px;
  padding: 0 24px;
  border: 1px solid var(--accent);
  border-radius: 3px;
  background: var(--accent);
  color: var(--white);
  font-size: 15px;
  font-weight: 700;
  transition: background 0.2s ease, border-color 0.2s ease;
}

.submit-button:hover {
  background: var(--accent-hover);
  border-color: var(--accent-hover);
}

@media (max-width: 1024px) {
  .contact-grid {
    grid-template-columns: repeat(2,minmax(0,1fr));
  }

  .inquiry-panel {
    grid-template-columns: 1fr;
  }

  .inquiry-info,
  .business-form {
    padding: 38px 30px;
  }
}

@media (max-width: 820px) {
  .contact-hero-inner {
    min-height: 300px;
    padding: 68px 0 48px;
  }

  .contact-hero h1 {
    font-size: 34px;
  }

  .contact-section {
    padding: 62px 0;
    scroll-margin-top: 122px;
  }

  .contact-heading {
    margin-bottom: 32px;
  }

  .contact-heading h2 {
    font-size: 27px;
  }

  .business-form {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 640px) {
  .contact-hero h1 {
    font-size: 30px;
  }

  .contact-grid {
    grid-template-columns: 1fr;
  }

  .contact-grid article {
    min-height: 0;
    border-right: 0;
  }

  .inquiry-panel {
    border-width: 3px;
  }

  .inquiry-info,
  .business-form {
    padding: 30px 22px;
  }

  .inquiry-info h3 {
    font-size: 28px;
  }
}
</style>
