git init
git add .
git commit -m "Обзвон СС"
git branch -M main
git remote add origin https://github.com/ТВОЙ_НИК/obzvon-ss.git
git push -u origin main
export type Question = {
  id: string;
  sets: string[];
  topic: string;
  prompt: string;
  answer: string;
  explain: string;
  choices: string[];
  open?: boolean;
};

export type Pack = {
  id: string;
  title: string;
  detail: string;
};

export const PACKS: Pack[] = [
  {
    id: "all",
    title: "Все комплекты",
    detail: "Одинаковые ответы склеены. Если в листах ответы расходятся, карточки останутся разными.",
  },
  {
    id: "struct",
    title: "Структуры и кодекс",
    detail: "Конституция, коллегия, прокуратура, график, госсволна раз в 10 минут.",
  },
  {
    id: "role",
    title: "Роль и служба",
    detail: "ДМ, ФСО, новости, митинг. Интервал госсволны здесь 10–60.",
  },
  {
    id: "order",
    title: "Распорядок",
    detail: "АФК, лицензии, чат департамента с 7 ранга, две очереди.",
  },
  {
    id: "situ",
    title: "IC и ситуации",
    detail: "Один и тот же лист в трёх таблицах: IC/OOC, истец, кактус.",
  },
  {
    id: "full",
    title: "Комплект на 20",
    detail: "Длинный лист с баллами: кодексы, слоты рангов, похищение, крыша.",
  },
];

export const OFFICIAL_BANK: Question[] = [
  {
    id: "greet-gov",
    sets: ["struct", "role", "order", "situ"],
    topic: "Вступление",
    prompt: "Как звучит приветствие на обзвоне старшего состава правительства?",
    answer:
      "Приветствую, уважаемый кандидат. Вы попали на обзвон на пост старшего состава Правительства. Представьтесь и расскажите немного о себе.",
    explain: "Это текст из шапки листов. Его проговаривает принимающий, но кандидат должен быть готов представиться сразу после него.",
    choices: [],
  },
  // ... ещё ~50 вопросов
];
