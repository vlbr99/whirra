<script>
  import ArrowDownWideNarrow from "lucide-svelte/icons/arrow-down-wide-narrow";
  import Plus from "lucide-svelte/icons/plus";
  import Trash2 from "lucide-svelte/icons/trash-2";
  import Pencil from "lucide-svelte/icons/pencil";
  import Mail from "lucide-svelte/icons/mail";
  import Instagram from "lucide-svelte/icons/instagram";
  import Facebook from "lucide-svelte/icons/facebook";
  import Linkedin from "lucide-svelte/icons/linkedin";
  import MoveRight from "lucide-svelte/icons/move-right";
  import MoveLeft from "lucide-svelte/icons/move-left";
  import Copy from "lucide-svelte/icons/copy";
  import Ban from "lucide-svelte/icons/ban";
  import Check from "lucide-svelte/icons/check";
  import User from "lucide-svelte/icons/user";
  import Menu from "lucide-svelte/icons/menu";
  import CalendarDays from "lucide-svelte/icons/calendar-days";
  import MapPin from "lucide-svelte/icons/map-pin";
  import Moon from "lucide-svelte/icons/moon";
  import Sun from "lucide-svelte/icons/sun";
  import Clock3 from "lucide-svelte/icons/clock-3";
  import Folder from "lucide-svelte/icons/folder";
  import File from "lucide-svelte/icons/file";
  import Heart from "lucide-svelte/icons/heart";
  import ArrowDownToLine from "lucide-svelte/icons/arrow-down-to-line";
  import ChevronDown from "lucide-svelte/icons/chevron-down";
  import Minus from "lucide-svelte/icons/minus";
  import Bookmark from "lucide-svelte/icons/bookmark";
  import Github from "lucide-svelte/icons/github";
  import MessageCircle from "lucide-svelte/icons/message-circle";
  import X from "lucide-svelte/icons/x";

  import { copy } from "svelte-copy";

  let copy_it = (e) => {
    e.target.textContent = "Copied";
    setTimeout(() => {
      e.target.textContent = "Copy code";
    }, 500);
  };
</script>

<div class="icons_wrapper">
  <h1>Icons</h1>
  <p>
    Icons are small graphical elements that visually represent actions,
    features, or content. They enhance user interfaces by making navigation
    intuitive and reducing the need for text labels.
  </p>
  <p>Icons from: <a href="https://lucide.dev/" target="_blank">Lucide</a></p>
  <div class="icon_divs">
    <div>
      <ArrowDownWideNarrow />
      <p>
        import ArrowDownWideNarrow from
        'lucide-svelte/icons/arrow-down-wide-narrow';
      </p>
      <button
        onclick={copy_it}
        use:copy={`import ArrowDownWideNarrow from 'lucide-svelte/icons/arrow-down-wide-narrow';`}
        >Copy code</button
      >
    </div>
    <div>
      <ArrowDownToLine />
      <p>
        import ArrowDownToLine from 'lucide-svelte/icons/arrow-down-to-line';
      </p>
      <button
        onclick={copy_it}
        use:copy={`import ArrowDownToLine from 'lucide-svelte/icons/arrow-down-to-line';`}
        >Copy code</button
      >
    </div>
    <div>
      <ChevronDown />
      <p>import ChevronDown from 'lucide-svelte/icons/chevron-down';</p>
      <button
        onclick={copy_it}
        use:copy={`import ChevronDown from 'lucide-svelte/icons/chevron-down';`}
        >Copy code</button
      >
    </div>
    <div>
      <MoveLeft />
      <p>import MoveLeft from 'lucide-svelte/icons/move-left';</p>
      <button
        onclick={copy_it}
        use:copy={`import MoveLeft from 'lucide-svelte/icons/move-left';`}
        >Copy code</button
      >
    </div>
    <div>
      <MoveRight />
      <p>import MoveRight from 'lucide-svelte/icons/move-right';</p>
      <button
        onclick={copy_it}
        use:copy={`import MoveRight from 'lucide-svelte/icons/move-right';`}
        >Copy code</button
      >
    </div>
    <div>
      <Plus />
      <p>import Plus from 'lucide-svelte/icons/plus';</p>
      <button
        onclick={copy_it}
        use:copy={`import Plus from 'lucide-svelte/icons/plus';`}
        >Copy code</button
      >
    </div>
    <div>
      <Minus />
      <p>import Minus from 'lucide-svelte/icons/minus';</p>
      <button
        onclick={copy_it}
        use:copy={`import Minus from 'lucide-svelte/icons/minus';`}
        >Copy code</button
      >
    </div>
    <div>
      <Trash2 />
      <p>import Trash2 from 'lucide-svelte/icons/trash-2';</p>
      <button
        onclick={copy_it}
        use:copy={`import Trash2 from 'lucide-svelte/icons/trash-2';`}
        >Copy code</button
      >
    </div>
    <div>
      <Pencil />
      <p>import Pencil from 'lucide-svelte/icons/pencil';</p>
      <button
        onclick={copy_it}
        use:copy={`import Pencil from 'lucide-svelte/icons/pencil';`}
        >Copy code</button
      >
    </div>
    <div>
      <Copy />
      <p>import Copy from 'lucide-svelte/icons/copy';</p>
      <button
        onclick={copy_it}
        use:copy={`import Copy from 'lucide-svelte/icons/copy';`}
        >Copy code</button
      >
    </div>
    <div>
      <Folder />
      <p>import Folder from 'lucide-svelte/icons/folder';</p>
      <button
        onclick={copy_it}
        use:copy={`import Folder from 'lucide-svelte/icons/folder';`}
        >Copy code</button
      >
    </div>
    <div>
      <File />
      <p>import File from 'lucide-svelte/icons/file';</p>
      <button
        onclick={copy_it}
        use:copy={`import File from 'lucide-svelte/icons/file';`}
        >Copy code</button
      >
    </div>
    <div>
      <Clock3 />
      <p>import Clock3 from 'lucide-svelte/icons/clock-3';</p>
      <button
        onclick={copy_it}
        use:copy={`import Clock3 from 'lucide-svelte/icons/clock-3';`}
        >Copy code</button
      >
    </div>
    <div>
      <CalendarDays />
      <p>import CalendarDays from 'lucide-svelte/icons/calendar-days';</p>
      <button
        onclick={copy_it}
        use:copy={`import CalendarDays from 'lucide-svelte/icons/calendar-days';s`}
        >Copy code</button
      >
    </div>
    <div>
      <MapPin />
      <p>import MapPin from 'lucide-svelte/icons/map-pin';</p>
      <button
        onclick={copy_it}
        use:copy={`import MapPin from 'lucide-svelte/icons/map-pin';`}
        >Copy code</button
      >
    </div>
    <div>
      <Moon />
      <p>import Moon from 'lucide-svelte/icons/moon';</p>
      <button
        onclick={copy_it}
        use:copy={`import Moon from 'lucide-svelte/icons/moon';`}
        >Copy code</button
      >
    </div>
    <div>
      <Sun />
      <p>import Sun from 'lucide-svelte/icons/sun';</p>
      <button
        onclick={copy_it}
        use:copy={`import Sun from 'lucide-svelte/icons/sun';s`}
        >Copy code</button
      >
    </div>
    <div>
      <Heart />
      <p>import Heart from 'lucide-svelte/icons/heart';</p>
      <button
        onclick={copy_it}
        use:copy={`import Heart from 'lucide-svelte/icons/heart';`}
        >Copy code</button
      >
    </div>
    <div>
      <Bookmark />
      <p>import Bookmark from 'lucide-svelte/icons/bookmark';</p>
      <button
        onclick={copy_it}
        use:copy={`import Bookmark from 'lucide-svelte/icons/bookmark';`}
        >Copy code</button
      >
    </div>
    <div>
      <Mail />
      <p>import Mail from 'lucide-svelte/icons/mail';</p>
      <button
        onclick={copy_it}
        use:copy={`import Mail from 'lucide-svelte/icons/mail';`}
        >Copy code</button
      >
    </div>
    <div>
      <MessageCircle />
      <p>import MessageCircle from 'lucide-svelte/icons/message-circle';</p>
      <button
        onclick={copy_it}
        use:copy={`import MessageCircle from 'lucide-svelte/icons/message-circle';`}
        >Copy code</button
      >
    </div>
    <div>
      <Instagram />
      <p>import Instagram from 'lucide-svelte/icons/instagram';</p>
      <button
        onclick={copy_it}
        use:copy={`import Instagram from 'lucide-svelte/icons/instagram';`}
        >Copy code</button
      >
    </div>
    <div>
      <Facebook />
      <p>import Facebook from 'lucide-svelte/icons/facebook';</p>
      <button
        onclick={copy_it}
        use:copy={`import Facebook from 'lucide-svelte/icons/facebook';`}
        >Copy code</button
      >
    </div>
    <div>
      <Linkedin />
      <p>import Linkedin from 'lucide-svelte/icons/linkedin';</p>
      <button
        onclick={copy_it}
        use:copy={`import Linkedin from 'lucide-svelte/icons/linkedin';`}
        >Copy code</button
      >
    </div>
    <div>
      <Github />
      <p>import Github from 'lucide-svelte/icons/github';</p>
      <button
        onclick={copy_it}
        use:copy={`import Github from 'lucide-svelte/icons/github';`}
        >Copy code</button
      >
    </div>
    <div>
      <User />
      <p>import User from 'lucide-svelte/icons/user';</p>
      <button
        onclick={copy_it}
        use:copy={`import User from 'lucide-svelte/icons/user';`}
        >Copy code</button
      >
    </div>
    <div>
      <Menu />
      <p>import Menu from 'lucide-svelte/icons/menu';</p>
      <button
        onclick={copy_it}
        use:copy={`import Menu from 'lucide-svelte/icons/menu';`}
        >Copy code</button
      >
    </div>
    <div>
      <Check />
      <p>import Check from 'lucide-svelte/icons/check';</p>
      <button
        onclick={copy_it}
        use:copy={`import Check from 'lucide-svelte/icons/check';`}
        >Copy code</button
      >
    </div>
    <div>
      <Ban />
      <p>import Ban from 'lucide-svelte/icons/ban';</p>
      <button
        onclick={copy_it}
        use:copy={`import Ban from 'lucide-svelte/icons/ban';`}
        >Copy code</button
      >
    </div>
    <div>
      <X />
      <p>import X from 'lucide-svelte/icons/x';</p>
      <button
        onclick={copy_it}
        use:copy={`import X from 'lucide-svelte/icons/x';`}>Copy code</button
      >
    </div>
  </div>
</div>

<style>
  .icons_wrapper {
    display: flex;
    align-items: flex-start;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    width: 100%;
    max-width: 650px;
  }
  .icons_wrapper .icon_divs {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 20px;
    background-color: transparent;
  }
  .icons_wrapper div {
    color: white;
    background-color: rgb(22, 22, 22);
    padding: 5px;
    border-radius: 5px;
    width: 99%;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    justify-content: center;
    gap: 10px;
  }
  button {
    padding: 5px;
    border-radius: 4px;
    background-color: white;
    border: 0;
    cursor: pointer;
    width: 80px;
  }
  .icons_wrapper h1 {
    color: white;
    text-align: center;
  }
  .icons_wrapper p {
    color: gray;
  }
  .icons_wrapper p a {
    color: white;
  }
</style>
