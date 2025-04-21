<template>
    <div>
        <div class="container mx-auto">
            <div class="min-h-screen flex flex-col md:flex-row bg-white">
    
    <!-- Booking Form -->
    <div class="w-full md:w-1/2 p-8 flex flex-col justify-center">
      <h2 class="text-3xl font-bold mb-6">Book a Table</h2>
      <form class="space-y-4">
        <div>
          <label class="block mb-1 text-sm font-semibold">Select Date</label>
          <input type="date" class="w-full border px-4 py-2 rounded-md" />
        </div>
        <div>
          <label class="block mb-1 text-sm font-semibold">Select Time</label>
          <input type="time" class="w-full border px-4 py-2 rounded-md" />
        </div>
        <div>
          <label class="block mb-1 text-sm font-semibold">Guests</label>
          <select class="w-full border px-4 py-2 rounded-md">
            <option>1 Guest</option>
            <option>2 Guests</option>
            <option>3 Guests</option>
            <option>4+ Guests</option>
          </select>
        </div>
        <div>
          <label class="block mb-1 text-sm font-semibold">Table Type</label>
          <select class="w-full border px-4 py-2 rounded-md">
            <option>Indoor</option>
            <option>Outdoor</option>
            <option>Private Room</option>
          </select>
        </div>
        <div>
          <label class="block mb-1 text-sm font-semibold">Special Request</label>
          <textarea class="w-full border px-4 py-2 rounded-md" rows="3" placeholder="Write here..."></textarea>
        </div>
        <button class="bg-green-600 text-white px-6 py-2 rounded-md hover:bg-green-700 transition w-full">
          Book Table
        </button>
      </form>
    </div>

    <!-- Image Section -->
    <div class="hidden md:block md:w-1/2">
      <img src="/images/cozy-restaurant.jpg" alt="Restaurant" class="w-full h-full object-cover" />
    </div>

  </div>
        </div>
    </div>
</template>