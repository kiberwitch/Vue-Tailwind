<template>
    <div>
      <slot />
    </div>
  </template>
  
  <script>
  import { gsap } from 'gsap'
  import { ScrollTrigger } from 'gsap/ScrollTrigger'
  import { useScroll } from '@vueuse/core'
  
  gsap.registerPlugin(ScrollTrigger)
  
  export default {
    provide() {
      return {
        registerSection: this.registerSection,
        scrollToSection: this.scrollToSection
      }
    },
  
    data() {
      return {
        sections: [],
        scroll: null
      }
    },
  
    mounted() {
      this.scroll = useScroll(document.documentElement)
      this.initScrollEffects()
    },
  
    methods: {
      registerSection(section) {
        this.sections.push(section)
      },
  
      scrollToSection(id) {
        const section = this.sections.find(s => s.id === id)
        if (!section) return
  
        const { top } = section.$el.getBoundingClientRect()
        const startY = window.pageYOffset
        const targetY = startY + top - 80 // 80px - отступ под header
  
        gsap.to(window, {
          duration: 1.2,
          scrollTo: { y: targetY, autoKill: false },
          ease: "power3.inOut",
          onStart: () => {
            // Эффект "замедления" соседних секций
            this.sections.forEach(s => {
              if (s.id !== id) {
                gsap.to(s.$el, {
                  duration: 0.8,
                  opacity: 0.6,
                  scale: 0.98,
                  y: s.id < id ? -20 : 20,
                  ease: "power2.out"
                })
              }
            })
          },
          onComplete: () => {
            // Возвращаем нормальное состояние
            gsap.to(".content-section", {
              opacity: 1,
              scale: 1,
              y: 0,
              duration: 0.5
            })
          }
        })
      },
  
      initScrollEffects() {
        this.sections.forEach((section, i) => {
          ScrollTrigger.create({
            trigger: section.$el,
            start: "top center",
            end: "bottom center",
            onEnter: () => this.animateSectionEnter(section.$el),
            onLeaveBack: () => this.animateSectionLeave(section.$el)
          })
        })
      },
  
      animateSectionEnter(el) {
        gsap.from(el, {
          duration: 0.8,
          opacity: 0,
          y: 100,
          rotateX: 5,
          ease: "back.out(1.2)"
        })
      },
  
      animateSectionLeave(el) {
        gsap.to(el, {
          duration: 0.6,
          opacity: 0.3,
          scale: 0.95,
          ease: "power1.in"
        })
      }
    }
  }
  </script>