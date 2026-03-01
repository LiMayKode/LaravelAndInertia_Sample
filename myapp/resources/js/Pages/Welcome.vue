<script setup>
import { Head, Link } from '@inertiajs/vue3';

const personalInfo = {
    name: 'Lloyd',
    title: 'Full Stack Developer',
    skills: ['Laravel', 'Vue.js', 'Inertia', 'TypeScript', 'Node.js', 'PHP']
};

const projects = [
    {
        name: 'Dashboard',
        url: '/dashboard',
        icon: 'M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6',
        position: 'top-10 right-10 sm:top-16 sm:right-16'
    },
    {
        name: 'Portfolio',
        url: '/portfolio',
        icon: 'M4 16l4.586-4.586a2 2 0 012.828 0L16 16m-2-2l1.586-1.586a2 2 0 012.828 0L20 14m-6-6h.01M6 20h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z',
        position: 'bottom-10 left-10 sm:bottom-16 sm:left-16'
    }
];
</script>

<template>
    <Head title="ロイド" />
    <div class="min-h-screen bg-gradient-to-br from-gray-900 via-black to-gray-900 flex items-center justify-center p-4 sm:p-6 lg:p-8 overflow-hidden">
        <!-- Project Blocks (scattered around) -->
        <div class="fixed inset-0 pointer-events-none">
            <Link 
                v-for="(project, index) in projects" 
                :key="index"
                :href="project.url"
                :class="['pointer-events-auto absolute group', project.position]"
            >
                <div class="backdrop-blur-xl bg-white/5 border border-white/10 rounded-2xl p-5 shadow-2xl hover:bg-white/10 hover:border-white/20 hover:scale-105 transition-all duration-300 w-28">
                    <div class="flex flex-col items-center gap-3">
                        <!-- Icon -->
                        <div class="w-12 h-12 flex items-center justify-center rounded-xl bg-gradient-to-br from-white/10 to-white/5 border border-white/10 group-hover:from-white/20 group-hover:to-white/10 transition-all duration-300">
                            <svg class="w-6 h-6 text-white/80 group-hover:text-white transition-colors" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" :d="project.icon" />
                            </svg>
                        </div>
                        <!-- Name -->
                        <span class="text-xs text-white/70 group-hover:text-white tracking-wide transition-colors">
                            {{ project.name }}
                        </span>
                    </div>
                </div>
            </Link>
        </div>
        
        <!-- Main Content -->
        <div class="relative w-full max-w-4xl z-10">
            <!-- Glow effect -->
            <div class="absolute inset-0 bg-white/10 blur-3xl rounded-full scale-150"></div>
            
            <!-- Glass card -->
            <div class="relative backdrop-blur-xl bg-white/5 border border-white/10 rounded-3xl shadow-2xl overflow-hidden">
                <!-- Desktop: Horizontal layout -->
                <div class="hidden md:flex items-center gap-8 lg:gap-12 px-8 lg:px-16 py-10 lg:py-12">
                    <!-- Left: ロイド -->
                    <div class="shrink-0">
                        <h1 class="text-5xl lg:text-7xl xl:text-8xl font-extralight text-white tracking-widest drop-shadow-lg">
                            ロイド
                        </h1>
                    </div>
                    
                    <!-- Divider -->
                    <div class="w-px h-20 lg:h-24 bg-gradient-to-b from-transparent via-white/30 to-transparent"></div>
                    
                    <!-- Right: Details -->
                    <div class="flex-1 space-y-4">
                        <div>
                            <h2 class="text-xl lg:text-2xl font-light text-white tracking-wide">{{ personalInfo.name }}</h2>
                            <p class="text-sm text-white/50 mt-1">{{ personalInfo.title }}</p>
                        </div>
                        
                        <div class="pt-2">
                            <p class="text-xs text-white/40 uppercase tracking-wider mb-3">Skills</p>
                            <div class="flex flex-wrap gap-2">
                                <span v-for="skill in personalInfo.skills" :key="skill" 
                                      class="px-3 py-1 text-xs text-white/80 bg-white/5 border border-white/10 rounded-full">
                                    {{ skill }}
                                </span>
                            </div>
                        </div>
                    </div>
                </div>
                
                <!-- Mobile: Vertical layout -->
                <div class="md:hidden px-6 py-8 space-y-6">
                    <!-- ロイド -->
                    <div class="text-center">
                        <h1 class="text-4xl sm:text-5xl font-extralight text-white tracking-widest drop-shadow-lg">
                            ロイド
                        </h1>
                    </div>
                    
                    <!-- Divider -->
                    <div class="w-16 h-px bg-gradient-to-r from-transparent via-white/30 to-transparent mx-auto"></div>
                    
                    <!-- Details -->
                    <div class="space-y-4 text-center">
                        <div>
                            <h2 class="text-lg sm:text-xl font-light text-white tracking-wide">{{ personalInfo.name }}</h2>
                            <p class="text-sm text-white/50 mt-1">{{ personalInfo.title }}</p>
                        </div>
                        
                        <div class="pt-2">
                            <p class="text-xs text-white/40 uppercase tracking-wider mb-3">Skills</p>
                            <div class="flex flex-wrap justify-center gap-2">
                                <span v-for="skill in personalInfo.skills" :key="skill" 
                                      class="px-3 py-1 text-xs text-white/80 bg-white/5 border border-white/10 rounded-full">
                                    {{ skill }}
                                </span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
