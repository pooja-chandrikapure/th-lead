<template>
    <div class="min-h-screen w-full flex flex-col items-center justify-center px-4 pb-20" style="background: linear-gradient(160deg, #f0f7ee 0%, #d4edda 50%, #b8dfc4 100%);">

        <!-- Gold accent line -->
        <!-- <div style="width: 48px; height: 3px; background: linear-gradient(90deg, #b8860b, #ffd700, #b8860b); border-radius: 2px; margin-bottom: 20px;"></div> -->

        <!-- Headline -->
        <h1 class="text-center font-bold mb-3" style="font-family: 'Georgia', serif; font-size: clamp(1.5rem, 4vw, 2.4rem); color: #1a2e1a; letter-spacing: -0.3px;">
            Get Free 7-Day Access To<br>
            <span style="color: #b8860b;">Gold AutoBot</span>
        </h1>

        <!-- Subheadline -->
        <p class="text-center mb-8" style="font-size: 0.95rem; color: #4a6741; max-width: 400px; line-height: 1.6;">
            We're currently providing complimentary access to a limited number of Gold traders.
        </p>

        <!-- Card -->
        <div class="w-full" style="max-width: 420px; background: #fff; border-radius: 20px; padding: 32px 28px; box-shadow: 0 4px 24px rgba(0,0,0,0.08); border: 1px solid rgba(184,134,11,0.15);">

            <!-- Card Header -->
            <div class="card-header">
                <!-- <div style="width: 44px; height: 44px; background: linear-gradient(135deg, #ffd700, #b8860b); border-radius: 50%; margin: 0 auto 10px; display: flex; align-items: center; justify-content: center;">
                    <span style="font-size: 20px;">✦</span>
                </div> -->
                 <img
                    src="../../public/gold-img.jpeg"
                    alt="Mahadev Capital Logo"
                    class="card-logo"
                />
                <h2 class="card-title font-semibold text-[20px]">Gold Autobot</h2>
            </div>

            <!-- Divider -->
            <div style="border-top: 1px solid #f0ebe0; margin-bottom: 0px;"></div>

            <!-- What Happens Next -->
            <p style="text-align: center; font-size: 0.7rem; font-weight: 700; letter-spacing: 2px; text-transform: uppercase; color: #9a8c6a; margin-top: 8px; margin-bottom: 16px;">
                What Happens Next?
            </p>

            <ol style="list-style: none; padding: 0; margin: 0 0 20px;">
                <li v-for="(step, index) in steps" :key="index"
                    style="display: flex; align-items: center; gap: 12px; padding: 9px 0; border-bottom: 1px solid #f5f2eb;">
                    <span style="flex-shrink: 0; width: 26px; height: 26px; border-radius: 50%; background: #fdf6e3; border: 1px solid #e8d98a; color: #b8860b; font-size: 0.75rem; font-weight: 700; display: flex; align-items: center; justify-content: center;">
                        {{ index + 1 }}
                    </span>
                    <span style="font-size: 0.9rem; color: #3a3a3a;">{{ step }}</span>
                </li>
            </ol>

            <!-- Info note -->
            <p class="text-gray-700 text-[13px] md:text-[14px] font-semibold " style="text-align: center; margin-bottom: 22px; line-height: 1.5;">
                Contact our team to receive access &amp; onboarding details.
            </p>

            <!-- CTA Button -->
            <button @click="openTg"
                style="width: 100%; padding: 13px; border-radius: 50px; border: none; background: linear-gradient(135deg, #c9a227, #b8860b); color: #fff; font-size: 0.9rem; font-weight: 700; letter-spacing: 1px; cursor: pointer; transition: opacity 0.2s;"
                onmouseover="this.style.opacity='0.88'"
                onmouseout="this.style.opacity='1'">
                GET ACCESS DETAILS
            </button>

        </div>

        <!-- Footer note -->
        <!-- <p style="margin-top: 20px; font-size: 0.75rem; color: #6a8c6a; text-align: center;">
            Limited spots available · No credit card required
        </p> -->

    </div>
</template>

<script setup>
const steps = [
    'Contact our team',
    'Check your eligibility',
    'Receive access details',
    'Start your 7-day trial',
]

const openTg = () => {
    if (window.fbq) {
        window.fbq('track', 'Lead')
    }

    const greetings = ["Hi", "Hello", "Hey"]
    const baseMessages = [
        "I'd like to know how I can get the 7-day Gold AutoBot access.",
        "can you share the details for the Gold AutoBot free access?",
        "I’m interested in the Gold AutoBot. How do I get started?",
        "I’d like to check if I’m eligible for the Gold AutoBot access.",
        "I saw your Gold AutoBot offer. Can you share the access process?",
        "I’m interested in trying the Gold AutoBot. What are the next steps?",
        "can you guide me on how to activate the 7-day access?",
        "I’d like to learn more about the Gold AutoBot and the trial access.",
        "I’m interested in exploring the Gold AutoBot. Can you share the details?",
        " I’d like to receive the Gold AutoBot access details and eligibility requirements."
    ]

    const randomGreeting = greetings[Math.floor(Math.random() * greetings.length)]
    const randomBase = baseMessages[Math.floor(Math.random() * baseMessages.length)]
    const finalMsg = `${randomGreeting}, ${randomBase}`
    const encodedMsg = encodeURIComponent(finalMsg)

    window.open(`https://t.me/simran_g09?text=${encodedMsg}`, '_blank')
}
</script>

<style scoped>
.card-header {
  text-align: center;
  margin-bottom: 24px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.card-logo {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  margin-bottom: 10px;
}

.card-header {
  text-align: center;
  margin-bottom: 12px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
