<template>
  <div id="container">
    <ion-item-divider css-class="divider">
      <ion-label> Default Checkboxes </ion-label>
    </ion-item-divider>
    <!-- Default Checkbox -->
    <ion-checkbox></ion-checkbox>

    <!-- Disabled Checkbox -->
    <ion-checkbox disabled="true"></ion-checkbox>

    <!-- Checked Checkbox -->
    <ion-checkbox checked="true"></ion-checkbox>

    <!-- Checkbox Colors -->
    <ion-checkbox color="primary"></ion-checkbox>
    <ion-checkbox color="secondary"></ion-checkbox>
    <ion-checkbox color="danger"></ion-checkbox>
    <ion-checkbox color="light"></ion-checkbox>
    <ion-checkbox color="dark"></ion-checkbox>
    <ion-item-divider>
      <ion-label> List Checkboxes </ion-label>
    </ion-item-divider>
    <!-- Checkboxes in a List -->
    <ion-list>
      <ion-item v-for="(entry, index) in form" :key="index">
        <ion-label>{{ entry.val }}</ion-label>
        <ion-checkbox
          slot="start"
          @input="entry.checked = $event.target.value"
          :value="entry.isChecked"
        >
        </ion-checkbox>
      </ion-item>
    </ion-list>
  </div>
</template>

<script>
import {
  IonCheckbox,
  IonItem,
  IonLabel,
  IonList,
  IonItemDivider,
} from "@ionic/vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "CheckboxList",
  components: { IonCheckbox, IonItem, IonLabel, IonList, IonItemDivider },
  setup() {
    const form = [
      { val: "Pepperoni", isChecked: true },
      { val: "Sausage", isChecked: false },
      { val: "Mushroom", isChecked: false },
    ];

    return { form };
  },
});
</script>
<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

#container a {
  text-decoration: none;
}
.divider {
  --inner-padding-top: 20px;
}
</style>