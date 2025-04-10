<template>
  <div class="modal">
    <div class="modal-content">
      <div class="modal-header">
        <h2>Start your 30-day trial <span class="crown">👑</span></h2>
        <p>
          Studio offers a whole set of advanced writing and outlining features.
        </p>
      </div>

      <div class="plans">
        <div 
          v-for="plan in plans" 
          :key="plan.name" 
          class="plan-card"
          :class="{'selected': isSelected(plan.name)}"
          @click="selectPlan(plan.name)"
        >
          <div class="corner-ribbon" />
          <h3>{{ plan.name }}</h3>
          <small class="plan-description">{{ plan.description }}</small>
          <ul class="features">
            <li v-for="feature in plan.features" :key="feature.name">
              <span class="emoji">{{ feature.emoji }}</span>
              <span>{{ feature.name }}</span>
            </li>
          </ul>
          <p class="price">
            <span v-if="plan.price !== undefined">
              Free for 30 days, then
              <a href="#">{{ plan.price }}/mo</a>
            </span>
            <span v-else>
              Free for everyone
            </span>
          </p>
        </div>
      </div>

      <div class="actions">
        <button class="secondary">Not yet</button>
        <button 
          :class="{'disabled': selectedPlan.length < 2}"
          class="primary" 
          :disabled="selectedPlan.length < 2"
        >
          Start free trial
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

interface Feature {
  name: string
  emoji: string
}

interface Plan {
  name: string
  description: string
  features: Feature[]
  price?: number
}

const plans: Plan[] = [
  {
    name: 'Essentials',
    description: 'For casual or early-stage writers.',
    features: [
      { name: '30-day history', emoji: '📅' },
      { name: 'Basic stats', emoji: '📊' },
      { name: 'One manuscript goal', emoji: '🎯' },
      { name: 'Writing features', emoji: '✍️' },
      { name: 'Typeset to PDF & EPUB', emoji: '📄' },
      { name: 'Planning Boards (card view)', emoji: '📝' },
      { name: 'Unlimited devices', emoji: '📱' },
      { name: 'Dark mode', emoji: '🌙' }
    ]
  },
  {
    name: 'Focused Writer',
    description: 'For motivated writers who love tracking progress.',
    price: 4.99,
    features: [
      { name: 'All features from Essential', emoji: '✨' },
      { name: 'Unlimited history', emoji: '⏳' },
      { name: 'Advanced stats', emoji: '📊' },
      { name: 'Custom goals', emoji: '🎯' },
      { name: 'Daily check-ins', emoji: '☑️' },
    ]
  },
  {
    name: 'Pro Organizer',
    description: 'For structured thinkers and outliners.',
    price: 7.99,
    features: [
      { name: 'All features from Essential', emoji: '✨' },
      { name: 'Unlimited Boards', emoji: '♾️' },
      { name: 'Unlimited Notes with Attributes', emoji: '📁' },
      { name: 'Pinned notes', emoji: '📌' },
      { name: 'List view', emoji: '👀' }
    ]
  },
  {
    name: 'Studio Pro',
    description: 'For power users who want it all.',
    price: 12.99,
    features: [
      { name: 'All features from Essential', emoji: '✨' },
      { name: 'All features from Craft', emoji: '🔧' },
      { name: 'All features from Outline', emoji: '🗂️' },
    ]
  }
]

let selectedPlan = ref(['Essentials'])

const isSelected = (planName: string) => {
  return selectedPlan.value.includes(planName)
}

const selectPlan = (planName: string) => {
  if (planName !== 'Essentials') {
    selectedPlan.value = ['Essentials', planName]
  }
}
</script>

<style scoped lang="scss" src="../styles/modal.scss" />
