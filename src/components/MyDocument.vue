<template>
  <div class="doc">
    <div class="list-1">
      <table class="sign">
        <tr>
          <td width="25%"></td>
          <td width="25%"></td>
          <td class="sign-col" width="25%">«Согласовано»<br> 
            с Управляющим советом <br>
            от____________20____г <br>
            Председатель УС:<br>
            ___________ <span v-if="chairman == ''">(Ф.И.О.)</span>{{chairman}} <br>
              подпись
          </td>
          <td class="sign-col" width="25%">«Утверждено» приказом <br>
              от___________20____г №_______ <br>
              <br>
              Должность: <span v-if="post == ''">(наименование должности)</span>{{post}} <br>
              <input type="text" v-model="post" placeholder="Введите должность">
          </td>
        </tr>
      </table>


      <h2>ПОЛОЖЕНИЕ<br>
        о разработке и реализации <br>
        специальной индивидуальной программы развития обучающегося </h2>


      <h3>I. Цель и основание разработки и реализации СИПР</h3>
      <div class="item">
        <div class="item__num">1.1.</div>
        <div class="item__text">
          Широкий диапазон особых образовательных потребностей 
          детей с умеренной, тяжелой, глубокой умственной отсталостью, 
          с ТМНР вызывает необходимость образования таких обучающихся по индивидуальной программе.
        </div>
      </div>
      <div class="item">
          <div class="item__num">1.2.</div>
          <div class="item__text">
            В соответствии с требованиями ФГОС образования обучающихся с интеллектуальными нарушениями и с учетом 
            2 варианта примерной АООП образования обучающихся с интеллектуальными нарушениями образовательная организация 
            разрабатывает специальную индивидуальную программу развития (далее СИПР) под руководством {{chairman}} в должности {{post}}.
          </div>
      </div>
      <div class="item">
        <div class="item__num">1.3.</div>
        <div class="item__text">
          Целью реализации СИПР является обретение обучающимся таких жизненных компетенций, которые позволяют ему достигать 
          максимально возможной самостоятельности в решении повседневных жизненных задач, обеспечивают его включение в жизнь 
          общества на основе индивидуального поэтапного, планомерного расширения жизненного опыта и повседневных социальных 
          контактов в доступных для него пределах.
        </div>
      </div>
      <h3>II. Организация разработки СИПР</h3>
      <div class="item">
        <div class="item__num">2.1.</div>
        <div class="item__text">
          При поступлении ребенка в образовательную организацию специалисты проводят психолого-педагогическое обследование с целью последующей разработки СИПР и создания оптимальных условий ее реализации.
        </div>
      </div>
      <div class="item">
        <div class="item__num">2.2.</div>
        <div class="item__text">
          На основе результатов психолого-педагогического обследования ребенка, проводимого специалистами образовательной организации, составляется психолого-педагогическая характеристика ребенка, в которой дается оценка его актуального состояния развития и определяется зона ближайшего развития обучающегося.
        </div>
      </div>
      <div class="item">
        <div class="item__num">2.3.</div>
        <div class="item__text">
          Структура характеристики включает: <span v-if="selectedElements1 == undefined">(выберите ниже)</span><br>

          <v-select 
            multiple
            label="text" 
            :options="elements1" 
            v-model="selectedElements1"
            class="mySelects"
          ></v-select>
          <ul>
            <li v-for="selectedElement in selectedElements1" :key="selectedElement.id">
            {{selectedElement.text}}</li>
          </ul>

        </div>
      </div>
      <div class="item">
        <div class="item__num">2.4.</div>
        <div class="item__text">
          Программа сотрудничества специалистов с семьей обучающегося включает перечень направлений сотрудничества, мероприятий и форм сотрудничества организации и семьи обучающегося, а также частоту и сроки проведения мероприятий.
          <p>Программа сотрудничества специалистов с семьей обучающегося предусматривает: <span v-if="selectedElements2 == undefined">(выберите ниже)</span></p>
          <v-select 
              v-model="selectedElements2" 
              label="text" 
              :options="elements2"
              class="mySelects"
          ></v-select>
          <ul v-if="selectedElements2 !== undefined">
            <li>{{selectedElements2.text}}</li>
          </ul>
        </div>
      </div>
    </div>
    <div class="list-2">
      <h3>III. Организация реализации СИПР</h3>
      <div class="item">
        <div class="item__num">3.1.</div>
        <div class="item__text">
          Реализация СИПР осуществляется группой, в которую входят те же специалисты, которые разрабатывали индивидуальную 
          программу развития, и родителями (законными представителями) обучающегося.
        </div>
      </div>
      <div class="item">
        <div class="item__num">3.2.</div>
        <div class="item__text">
          К анализу результатов обучения привлекаются члены семьи обучающегося. В ходе аттестации дается согласованная оценка 
          достижений ребёнка в сфере жизненных компетенций.
        </div>
      </div>
    </div>
    <div class="annex">
      <p class="annex-title">Приложение №1</p>
      <table class="annex-table">
        <caption class="annex-table__cap">Пример классификатора жизненных компетенций</caption>
        <tbody>
          <tr>
            <th width="20%">Критерии</th>
            <th width="20%">Параметры оценки</th>
            <th width="60%">Индикаторы</th>
          </tr>
          <tr>
            <td rowspan="9">Овладение социально -
                бытовыми умениями,
                используемыми в
                повседневной жизни
            </td>
            <td rowspan="3">Сформированность
                социально-бытовых умений в домашних условиях
            </td>
            <td>Способность применять социально бытовые умения под руководством взрослого</td>
          </tr>
          <tr>
            <td>Способность обращаться за помощью при формировании социально-бытовых умений </td>
          </tr>
          <tr>
            <td>Способность применять социально – бытовые умения самостоятельно </td>
          </tr>
          <tr>
            <td rowspan="3">Сформированность
                социально-бытовых умений в ближайшем окружении (в школе, во дворе)
            </td>
            <td>Способность применять социально бытовые умения под руководством взрослого школе, во дворе</td>
          </tr>
          <tr>
            <td>Способность обращаться за помощью при
                формировании социально - бытовых умений.
            </td>
          </tr>
          <tr>
            <td>Способность применять социально – бытовые умения самостоятельно</td>
          </tr>
          <tr>
            <td rowspan="3">Сформированность
              социально – бытовых умений в более широкой жизненной ориентации (в
              социуме)
            </td>
            <td>Способность применять социально бытовые умения под руководством взрослого</td>
          </tr>
          <tr>
            <td>Способность обращаться за помощью при
              формировании социально - бытовых умений.
            </td>
          </tr>
          <tr>
            <td>Способность применять социально – бытовые умения самостоятельно</td>
          </tr>
          <tr>
            <td rowspan="8">Владение навыками
              коммуникации и принятыми
              ритуалами социального
              взаимодействия (т.е. самой
              формой поведения, его социальным рисунком), в том числе с использованием
              информационных
              технологий
            </td>
            <td rowspan="3">Сформированность навыков коммуникации со взрослыми</td>
            <td>Способность инициировать и поддерживать
              коммуникацию со взрослыми
            </td>
          </tr>
          <tr>
            <td>Способность применять адекватные способы поведения в разных ситуациях </td>
          </tr>
          <tr>
            <td>Способность обращаться за помощью</td>
          </tr>
          <tr>
            <td rowspan="3">сформированность навыков
              коммуникации со
              сверстниками
            </td>
            <td>Способность инициировать и поддерживать
              коммуникацию сверстниками
            </td>
          </tr>
          <tr>
            <td>Способность применять адекватные способы поведения в разных ситуациях</td>
          </tr>
          <tr>
            <td>Способность обращаться за помощью</td>
          </tr>
          <tr>
            <td>владение средствами
            коммуникации
            </td>
            <td>Способность использовать разнообразные средства коммуникации согласно ситуации</td>
          </tr>
          <tr>
            <td>адекватность
              применения ритуалов
              социального
              взаимодействия
            </td>
            <td>Способность правильно применить ритуалы
              социального взаимодействия согласно
              ситуации
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import vSelect from "vue-select";
import "vue-select/dist/vue-select.css";

export default {
  name: 'MyDocument',
  props: ['chairman'],
  components: {
    "v-select": vSelect
  },
  data() {
    return {
      post: '',
      elements1: [
        {id: 1, text: 'год обучения в образовательной организации'},
        {id: 2, text: 'сведения о семье (социально-бытовые условия, взаимоотношения в семье, отношение к ребенку)'},
        {id: 3, text: 'данные о физическом здоровье, двигательном и сенсорном развитии ребенка'},
        {id: 4, text: 'представления об окружающем мире (о себе, ближайшем окружении, природном, растительном, социальном мире)'},
        {id: 5, text: 'выводы по итогам оценки'},
      ],
      elements2: [
        {id: 1, text: 'психологическую поддержку семьи, консультации по всем вопросам оказания психолого-педагогической помощи ребенку'},
        {id: 2, text: 'просвещение по вопросам воспитания и обучения ребенка-инвалида'},
        {id: 3, text: 'регулярные контакты родителей и специалистов в течение всего учебного года и др'}
      ],
      selectedElements1: undefined,
      selectedElements2: undefined
    }
  },
  // computed: {
  //   selectedResult(selectedElements1) {
  //     selectedElements1.forEach(element => console.log(element));
  //   }
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
%for-td {
  border: thin solid black;
  padding: 5px;
  font-weight: normal;
}

.doc {
  margin: 0 5px 0 5px;
}
h2 {
  font-size: 14px;
}
h3 {
  font-size: 14px;

  &:not(:first-child) {
  margin-top: 1rem;
  }
}
h4 {
  font-size: 12px;
}

.item {
  display: flex;

  &:not(:first-child) {
    margin-top: 14px;
  }

  &__text {
    margin-left: 10px;
    text-align: justify;
    width: 100%;

    & > p {
      margin-bottom: 0;
    }
  }
}

input {
  font-size: 8px;
}

.mySelects {
  margin: 20px 0;
}

p {
  margin: 1rem 0 1rem 0;
}

.list-1 {
  page-break-after: always;
}

.annex {
  margin-top: 50px;

  &-title {
    font-size: 12px;
    margin: 0 10px;
    text-align: right;
  }

  &-table {
    font-size: 12px;
    font-weight: normal;
    text-align: center;
    caption-side: top;
    border-spacing: 0px;
    width: 100%;
    border: thin solid black;

    & td, & th {
      @extend %for-td;
    }

    &__cap {
      font-weight: bold;
      font-size: 12px;
      text-align: center;
      padding: 10px;
    }
  }
}

.sign {
  font-size: 11px;
  width: 100%;
  border: none;
  margin: 0;
  caption-side: top;
  border-spacing: 0px;
  margin-bottom: 50px;

  &-col {
    @extend %for-td;

    &:last-child {
      border-left: none;
    }
  }
}

@media print {
  input {
    display: none;
  }

  .mySelects {
    display: none;
  }
}
  
</style>